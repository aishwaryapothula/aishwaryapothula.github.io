---
layout: blog
title: Lamports Logical Clocks To Derive A Total Order Of Events
---


# Lamports Logical Clocks To Derive A Total Order Of Events

Totally ordered Multicasting Algorithm using Lamport&#39;s
Update message is time stamped with sender&#39;s logical time
Update message is multicast (including sender itself)
When a message is received It is put into local queue ordered according to timestamp, Multicast acknowledgments

_Why_ _acknowledgments_ _are needed_?

Acknowledgments are needed for each message when using Lamport&#39;s logical clocks to derive a total order of events in distributed systems as they ensure that messages are processed in the same order at each replica of the resource. The ordering of the acknowledgments according to the following

P<sub>i</sub> sends an acknowledgment to P<sub>j</sub> if
P<sub>i</sub> has not made an update request
P<sub>i</sub>&#39;s identifier is greater than P<sub>j</sub>&#39;s identifier P<sub>i</sub>&#39;s update has been processed;

And

Delivering the message to applications only when it is at the head of the queue and has been acknowledged by all involved processes ensures that updates are processed in the same order at all the servers.
