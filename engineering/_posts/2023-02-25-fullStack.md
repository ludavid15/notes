---
layout: post
title: Full Stack Development on AWS
permalink: /fullStack/
mathjax: true
except_separator: <!--more-->
categories: engineering
---

In the frontend post, we explored React and how to build a dynamic website with it. Now let's focus on developing a full stack application, using React for the frontend, and AWS to support the backend. This is a bit of a work in progress, and presents only one way to do this. There are alot more tools available, and depending on the requirements of your site you may choose a different architecture entirely. 

### Overview

Let's begin by discussing the pieces of our project. There's a lot of different tools required to make this whole thing work. 

#### 1. React Code

This is the javascript code that makes up the frontend. A bundling tool turns our React code into the build version that your browser will run. 

#### 2. AWS S3 Bucket

This is a file hosting service that we'll use to store our React Code. When a user tries to access our website, they'll be sent the React code stored in S3 (technically we're actually storing the build version, not the source React scripts).

#### 3. AWS Route 53

This is a DNS service that connects the human readable domain name (e.g. www.coolwebsite.com), to the actual machine readable IP address (93.184.216.34). Behind the scenes, a DNS service is doing a lot of lookup to make this connection. 

#### 4. AWS Cloudfront

This is an optional service, but recommended. Cloudfront is a content delivery network, which gives you more options and control in how users access your website. One feature that Cloudfront enables is HTTPS instead of HTTP (the S stands for secure).

#### 5. AWS DynamoDB

A noSQL database service. This is our primary repository for user data. Databases provide a nice way to manage and read from large datasets. The benefit of using an AWS database is that it is managed for us, which means all we have to take care of is our data structure. 

#### 6. AWS API Gateway

Since we're using a database service, we'll need an API to fetch/write data from/to the database. Now, we could use the AWS SDK to interect directly with our database from our React frontend, but this is not recommended. Doing so introduces issues with security, scability, and cost. Instead, we'll use AWS API Gateway to handle interactions with DynamoDB. This exposes a set of well-defined API endpoints that our client-side application can interact with. This allows us to centralize our application logic and ensure that our backend services are properly secured and scaled to meet demand.

> AWS API Gateway primarily works with REST. For my application, REST is more than sufficient. But this is just one type of API; another popular alternative is GraphQL, which provides a richer way to query data. 

#### 7. AWS Lambda

This is an optional component. If we are only making simple read/write requests to our database, we can skip this. However, if we need complex functions, we can use AWS Lambda. AWS Lambda is a serverless compute service, which runs a function based on a trigger. This provides a nice way to code more complex processes.  

<p class="message">
There's another AWS tool called AWS amplify which helps you quickly setup a website. It's worth noting that all it does is basically set up the aforementioned resources for you. In other words, it's not a fundamental service, but rather a tool to help setup other services. If you know what you're doing, this is a very handy tool, but if you're new I recommend building everything from scratch. This will help you learn and also avoid suprise fees. 
</p>


### HTTP Methods

HTTP is an application layer communication protocol used for transferring data on the internet. Or, another way to think about it, HTTP is how the user makes requests from the server. There are four basic methods available in HTTP.

1. Create
2. Read
3. Update
4. Delete

In a request, we will need to specify the: Method, URL, and Data (if relevant). 


### Databases

DynamoDB is a managed noSQL database service. Setting it up is not so bad, but in the context of an application, it's important to consider the *cost* of reading and writing. Here's an example to illustrate. Maybe you use DynamoDB as a database of your employees. You only write to it when you hire someone new, and you only read from it once a week to generate payrolls. This would be pretty cheap. But let's say now that you build a frontend application which everytime it renders makes a read request to your database. This is a pretty dramatic increase in frequency, and could be expensive. Instead, consider how up-to-date you really need your frontend. Maybe instead of making a read request every time it renders, it can update from the database once a day, and store this result somewhere else. 