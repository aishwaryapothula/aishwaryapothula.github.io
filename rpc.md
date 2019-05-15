---
layout: default
title: Advantages and Disadvantages Of RPC And Message-Oriented Communication
---

# Advantages and Disadvantages Of RPC And Message-Oriented Communication

**RPC Advantages**

- Allows for offloading computation from devices to servers (which have more compute    capabilities)

-  Provides functionality to harness functions that just cannot be run locally

-  Increases access transparency through client and server stubs. The internal message passing mechanism of RPC is hidden from the user.

-  Remote procedure calls support process oriented and thread oriented models.

-  The effort to maintain code is minimum in remote procedure calls.

-  Remote procedure calls can be used in distributed environment and in local environment

-  Simplicity of implementation and straightforward mechanism

**RPC Disadvantages**

-  Heterogeneity in client and server such as different versions of OS, different languages, different hardware architecture etc makes it difficult to implement RPC

-  Synchronous data exchange-A client is blocked till its request has been processed at the server

-  Difficult to scale parts of the system and deal with service failures- requires a lot of bandwidth making it expensive. There is no flexibility in RPC for hardware architecture due to tight coupling of producers and consumers

-  No Built-in support for one-many communications

-  With RPC data consistency can be assured

**Message Oriented Communication Advantages**

-  Systems are efficient in coping with traffic bursts

-  Lesser bandwidth required for a interaction than for an RPC interaction

-  Remote systems need not be available for calling program to send a message

-  Loose coupling between producers and consumers-allows flexible systems to scale

-  Offers flexible integration of multiple systems

**Message Oriented Communication Disadvantages**

-  Major disadvantage is that it requires a message transfer agent in the architecture- can lead to performance degradation, make system expensive to maintain

-  Loose-coupling also creates problems- with communication being asynchronous, the calling client can continue to load work upon the recipient until the resources need to complete the first task are depleted and task fails.

-  Communication being asynchronous, there is more probability for temporal inaccuracies in data
