---
layout: blog
title: Causally Order Events On Distributed Machines Using Logical Clocks
---

# Causally Order Events On Distributed Machines Using Logical Clocks

A logical clock is a mechanism to capture the chronological relationships in a distributed system. To implement a logical clock, every node in the distributed system should agree on the order in which events occur rather than the time at which they occurred

To implement Lamport&#39;s logical clocks, each process Pi maintains a local counter G. These counters are updated as follows steps:

a) Before executing an event Pi executes Gf- G+1.

b) When process Pi sends a message m to Pj it sets m&#39;s timestamp ts (m) equal to G after having executed the previous step.

c) Upon the receipt of a message m, process Pj adjusts its own local counter as 0f- max{0,ts(m)}, after which it then executes the first step and delivers the message to the application.

Before delving into how logical clocks can be used to order causally related events, it is essential to understand the &quot;happens before&quot; relation and causal relation.

_&quot;happens-before&quot;_

---\&gt; denotes the &quot;happens before&quot; relation and it is identified as follows:

-  A and B are within the same process(same sequential thread of control) and A

occurred before B

- A is the event of sending a message M and B is the receiving M by another

process

- If A---\&gt;B and B---\&gt;c then A---\&gt;C

_Causal Relation_

Two events A and B are said to be causally related if there exists a &quot;happens before&quot; relationship i.e A---\&gt;B

_Ordering Causally Related Events_

A logical clock assigns a clock value Ci(event) to each event in a process i in the following ways such that causality is preserved (timestamps reflect the order of events)

_Partial Ordering_

If event A &quot;happens before&quot; event B ie A---\&gt;B then clock values are assigned such that clock(A)\&lt;clock(B) according to the following rules

• Each event A in i is time-stamped Ci(A)- the value of clock of process i when A occurred

• Ci is incremented by 1 for each event in i

• In addition, if A is a send of message m from process i to j, then on receive of m, Cj = max (Cj, Ci(A)+1) These events are considered causal.
