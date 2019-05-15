---
layout: blog
title: How Message-Queuing Model Can Help Design Of Distributed Systems
---

# How Message-Queuing Model Can Help Design Of Distributed Systems

Let&#39;s call a process which generates messages as a producer and a process which processes these messages a consumer. Message passing allows for processes to communicate and synchronize their actions without having to share the same address space.

Messages queueing stores messages in a queue, acting as a buffer, and routes them to a receiver who will process them. Message queueing helps simplify the design of distributed systems in the following ways

_Simplified Scaling_: Since a single queue can be shared between virtually any number of producers and consumers, systems can be scaled up quite easily buy spawning more processes and threads as long as they communicate using the same message queue.

_Enhanced Workload Distribution_: Each consumer controls its own flow and retrieves its messages from the queue when it is ready. Consequently, message queues enhance workload distribution. On the contrary, if the workload is preassigned, consumers which process quickly might stay idle while slow processing consumer might be overburdened with the workload.

_Machine failures handled_: Some message queueing applications set a specific amount of time for the consumer within which a message has to be processed and deleted from the queue. In the case of consumer failure, the message is automatically routed to another consumer after the time has elapsed.

_System Decoupling_: Queues are language-agnostic. A process written in a different language from the consumer can generate messages that can be processed by the consumer, making it easier to design distributed systems.
