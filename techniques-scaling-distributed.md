---
layout: default
title: Techniques For Scaling Distributed Systems
---

# Techniques For Scaling Distributed Systems

**Scaling Techniques**

There are presently three techniques used for scaling which attempt to solve some of the inherent problems in scaling but also have their own disadvantages. One of these scaling techniques or a combination of these scaling techniques are used by organizations depending on organizational priorities in relation to data consistency, allowable performance degradation, acceptable latency etc.

**Hiding Communication Latencies**

Communication latencies can be often mistaken for low remote server performance or capabilities. Consequently, hiding communication latencies becomes essential to achieving geographical scaling. There are two ways to hide communication latencies.

_Avoid (idly) Waiting for remote server response:_

Make use of asynchronous communication to execute other independent processes in the time it takes for the server response to arrive. When the response arrives an interrupt is executed to inform the client process of the response and special handler for completing the process.

_Pros:_
Communication latencies are hidden as client process is busy executing other     processes in the time the response comes

_Cons:_
Most interactive applications do not have any other processes to execute till the response arrive, making the solution irrelevant.

_Reduce server communication:_

One way to reduce server communication is to shift part of the server communication to the client side. An example is to shift the data validation in a form filling to the client side, instead of having to communicate with the server for each blank filled.

_Pros:_
Speeds up the execution of processes

**Distribution**

Distribution as a scaling technique involves partitioning a resource into smaller units and distributing it across the system. A good example is the way the internet Domain Name service is organized. The name space is hierarchically organized into a tree of non-overlapping zones, each of which only resolve names in their own zone.

_Pros:_
Distributes the burden on request handling
Increases transparency, strengthening the single system view

_Cons:_
Performance degradation

**Replication**

Replication as a scaling technique involves creating copies if resource components and distributing them across the system.

There is also a special case of replication called caching. It is similar to caching in the sense that caching involves having a copy of the resource in close proximity to the client. It is differs from replication in the sense that a caching decision is taken by a client and on demand whereas a replication decision is made by the owner of the resource and is preplanned. An example of caching would be a web browser storing a copy of a document whose validity has not been verified for sometime.

_Pros:_
Increases availability
Balances the load between components leading to an increased performance
Helps hide communication latencies in geographically distributed systems

Cons:
Maintaining data consistency for applications that require string consistency would be extremely difficult
Replication or caching for geographically distributed systems might require some kind of global synchronization which is highly impossible
