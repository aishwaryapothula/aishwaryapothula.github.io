---
layout: blog
title: Differences between distributed and parallel systems
---

# Differences between distributed and parallel systems

| **Distributed Systems** | **Parallel Systems** |
| --- | --- |
|   |
| Collection of independent computers that appear to its users as a single coherent system              . | Use of two or more processors (cores, computers) in combination to solve a single problem.                       . |
| Inherent support for fault tolerance but performance is affected                                         .. | Fault tolerance not inherent, can be provided by developer to a certain extent - checkpoint based fault tolerance |
| Provides support to basic operations such as broadcast, scatter, gather and reduce | Support richer set of collective operations                  . |
| Dynamic scaling of resources according to workload is easier | Dynamic allocation is provided in some frameworks but limited. |
| Supports ethernet by default                                                             .                                                                   .                 . | Supports high end communication protocols along with ethernet-can leverage high end performance from networks |
| Higher abstraction makes user/developer friendly | Lower abstraction gives higher control and higher performance |
| Machine acts as both server and client | Service is separate from clients |
| Workload-Loosely coupled distributed apps | Workload-High performance coordinated apps |

**However, the line seems to be blurring...**

The distinction between distributed systems and parallel systems seems to be diminishing as most systems today use a combination of distributed and parallel computing. For example, frameworks such as Hadoop are distributed systems with workers executing tasks on different machines but also leveraging each machine with some level of parallel computing.
