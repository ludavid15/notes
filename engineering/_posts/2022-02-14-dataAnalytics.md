---
layout: post
title: Data Analytics
permalink: /dataanalytics/
mathjax: true
except_separator: <!--more-->
categories: engineering
---

A collection of notes and lessons from the Google Data Analytics Certificate.

<!--more-->

### Overview

### The lifecyce of data. 

Why do we discuss the lifestyle of data? Because data analytics is not just about obtaining results, it's about collecting, managing, and then closing out a process. 

1. Plan
2. Capture
3. Manage
4. Analyze
5. Archive
6. Destroy


### Setting up the Problem

The best results come from a well defined question. And one way to build good questions is to use the SMART system:

1. Specific
2. Measurable
3. Action-oriented
4. Relevant
5. Time constrained

And finally, it's also worth considering the type of problem. Which of these are you trying to do?

1. Predict
2. Categorize
3. Detect outliers
4. Identify themes
5. Discover connections

Different objectives may lead to different problem setups and approaches. The better you understand what you are trying to do, the more tailored you can make your response. 

### Types of Data

1. Nominal vs Ordinal 
    1. Nominal - Choices/responses that don’t have a particular order (i.e. yes/no/maybe)
    2. Ordinal - Data that has an associated order (i.e. a scale or ranking).
2. Internal vs External (i.e. who owns the data? Does it come from outside your organization?)
3. Continuous vs Discrete
4. Quantitative vs Qualitative
5. Structures vs Unstructured (i.e. survey responses, vs pictures)
6. Primary vs Secondary


### Types of Data Modeling

1. **Conceptual data modeling** gives a high-level view of the data structure, such as how data interacts across an organization. For example, a conceptual data model may be used to define the business requirements for a new database. A conceptual data model doesn't contain technical details. 
2. **Logical data modeling** focuses on the technical details of a database such as relationships, attributes, and entities. For example, a logical data model defines how individual records are uniquely identified in a database. But it doesn't spell out actual names of database tables. That's the job of a physical data model.
3. **Physical data modeling** depicts how a database operates. A physical data model defines all entities and attributes used; for example, it includes table names, column names, and data types for the database.


### Data Integrity

Data integrity is something to keep in mind through the entire data analysis process. Data with integrity means that is accurate, complete, consistent, and trust-worthy. 

One common pitfall is to have biased data. This can occur if you're using a survey to collect data and use leading or vague questions. Some examples:
* Isn't it true that A had a negative effect on B?
* What's going on with A?

Other common pitfalls of the data cleaning process:

1. Overlooking missing values
2. Only looking at a subset
3. Losing track of objectives
4. Not fixing the root of the issue
5. Not analyzing the system
6. Not backing up your data prior to cleaning
7. Not accounting for cleaning time in budgeting
8. Not checking for spelling errors
9. Forgetting to document errors
10. Not checking for misfielded values


### Data Visualization

Principles of good data visualization:

1. Information
2. Story
3. Goal
4. Visual Form

You can also review your presentation with these questions:

1. What is the practical question?
2. What does the data say?
3. What does the visual say?

Finally, make sure to consider the use case. For instance, if we need to monitor new data as it comes in, an interactive dashboard with the proper backend support would be best. However, if we wanted historical data, a dashboard could be too complex. This is an example of how the visualization step is not independent of our initial setup. 

