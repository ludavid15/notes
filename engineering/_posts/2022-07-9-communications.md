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

#### ML-STD 1553

A traffic control protocol for managing information traffic from multiple sources on a shared physical line. 1553 requires a controlling bus computer (BC) and an addresses for each terminal. The underlying constraint of 1553 is that traffic is never parrallel. In other words, each terminal takes turns using the line, and ignores any information on the line while not actively in use. On any given 1553 line, there can be up to 31 *remote terminals* (RTs), each with their own *subaddresses*. Data transmission can happen in pretty much any direction:

1. Controller to RT
2. RT to Controller
3. RT to RT

> Being an older protocol, 1553 only has a bandwidth of around 1 Mbps

### Ethernet

Ethernet is another communications protocol, defined at the physical layer and data link layer. In contrast to 1553 which uses a shared bus topology, ethernet supports direct transmission paths between devices. The data link layer has two different aspects. There's the Logical Link Control (LLC) and the Media Access Control (MAC).

There are also two transmission modes:

1. Half Duplex - transmission is only allowed in 1 direction at any given moment.
2. Full Duplex - transmission is allowed in both directions at once.

> Standard ethernet has bandwidths of 100 Mbps, 1000 Mbps, or 10 Gbps. 

### SpaceWire

If you need the high bandwidth capability of ethernet, but also want something a bit more tailored to space applications, there's SpaceWire. This is a point to point network, and features better reliability than Ethernet. It's slightly less suitable for huge networks, but when you're talking about a spacecraft there are only a handful of nodes anyway. 


### RS-422

A point to point interface which transmits digital/bi-level information by changing the difference in voltage between two lines. This allows for higher data rates and lower noise in comparison to a single voltage line because we can achieve the same total change in the difference with only half the voltage change in each line. 

> RS422 has a typical bandwitch of up to 10 Mbps

### Miscellaneous Definitions

| Name      | Definition
|-          |-
|Bi-Level   |Consisting of two states (i.e. 0 and 1). In constrast to *analog*.
|Serial communication | Commmunication that consists of sending data one bit at a time. 


### Hardware

#### Traveling Wave Tube Amplifier

Often abbreviated to just TWTA, this is a device used for amplifying radio signals. Satellites often need this since they communicate over large distances.

#### Waveguide

TBD

#### Coax-Cable

TBD

### Message Security/Integrity

Besides protocols and hardware to manage communications, we'd should also think about ways to ensure security and check the integrity of what we communicate. But before jumping in further, I do want to highlight the distinction between integrity and authenticity. 

Integrity is a simple check to see if the data is complete, or it's accurate. Authenticity checks to ensure that data has not been modified in transit, or that it comes from the source/target you expect. Security measures usually help to ensure *authenticity* rather than integrity.  

An easy integrity check to start with is Parity. This is a single bit which tells you if there is an even or odd number of 1's in the transmitted signal. We can use this to check the integrity of a message.

Another integrity check we can do is called a checksum. A checksum function transforms some input and calculates an output. Strong checksum functions will produce unique outputs, even for similar inputs. If a receiver and transmitter both know the checksum function, they can each calculate the checksum value and by comparing the outputs, verify that the sent and received message are the same, without revealing the message itself. 



