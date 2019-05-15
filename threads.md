---
layout: blog
title: Threads Processes And Multi-Threading
---

# Threads Processes And Multi-Threading 


| Process | Thread |
| --- | --- |
| A program loaded into memory with all the resources it needs | An executable unit within a process                                       . |
| Allocated their own memory space.       . | Threads of a process operate within the address space of the process |
| More expensive to create as memory needs to be allocated | Easier to create since they do not require a separate memory space |
| Context switching between processes is more expensive | Context-switching between threads is less expensive                . |
| Process are heavy-weight operations | Threads are lighter weight operations                                      . |
| Process don&#39;t share memory with other processes. They are independent of each other                  . | Threads share memory with other threads of the same process. Operating in the same space, threads are interdependent. Threads separate concurrency from protection |
| Inter process communication is expensive | Inter thread communication can be faster as they share memory space |

**Multi-threading**

In multi-threading a process has multiple threads and tries to execute multiple parts of a program (threads) at the same time. It allows for maximum utilization of the CPU

_Benefits of Multi-threading_

_Reduced Resource usage_
All threads in a process share resources such as memory, data, files etc Threads require less overhead to create, maintain and manage than processes.

_Maximum utilization of CPU_
Exploits parallelism in a multi-processor system
Simultaneous and symmetric use of multi processors for computation and I/O

_Responsiveness_
Large or complex requests don&#39;t block other requests for services

_Improved throughput_
Many compute operations and I/O requests are executed within a single process

_Program structure simplification_
Complex program structures can be simplified as simple routines can be written for each activity
Allows for more adaptiveness to wide variation in user demands

_Improved Communication_
Useful in coordinating programs. Multiple threads of a process sharing memory allows for or low latency communication between separate tasks within a process
