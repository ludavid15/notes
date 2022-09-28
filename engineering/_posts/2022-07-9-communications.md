---
layout: post
title: Communications Technology
permalink: /Communications/
mathjax: true
except_separator: <!--more-->
categories: engineering
---

A random assortment of communications technology terms I've encountered over the years. Please keep in mind that electrical engineering and signal processing is *not* one of my subjects, so take everything here with a grain of salt. 

<!--more-->

1553: A traffic control protocol for managing information traffic from multiple sources on a shared physical line. 1553 requires a controlling computer and an addresses for each terminal. The underlying constraint of 1553 is that traffic is never parrallel. In other words, each terminal takes turns using the line, and ignores any information on the line while not actively in use. 

Bi-Level: consisting of two states (i.e. 0 and 1). In constrast to *analog*.

Serial communication: commmunication that consists of sending data one bit at a time.

RS-422: a point to point interface which transmits digital/bi-level information by changing the difference in voltage between two lines. This allows for higher data rates and lower noise in comparison to a single voltage line because we can achieve the same total change in the difference with only half the voltage change in each line. This is comparable to things like ethernet or USB. 



