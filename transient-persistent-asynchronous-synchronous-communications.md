---
layout: default
title: Transient Persistent Asynchronous Synchronous Communications
---

# Transient Persistent Asynchronous Synchronous Communications

**Persistent Communication**

In persistent communication, a communication server stores the message as long as it takes to deliver it to the receiver. It is not essential for the sending application to be running after it has submitted the message and it is not essential for the receiving application to be running when the message is submitted.

Persistent communication is preferred when all components are not continually connected, when communication networks are not reliable and when more mobility is needed.

**Transient Communication**

In transient communication, a communication server discards a message as soon as it cannot be delivered at the next server or at the receiver. It requires both the sending application and the receiving application to be running at the time of communication.

Typically, all transport level communication services offer only transient communication Asynchronous communication: It is called an synchronous communication when the sender moves on immediately after it has submitted its message for transmission. The message is stored by the middleware immediately upon submission.

Asynchronous communication is preferred when the sender can proceed without expecting an answer or when it is okay to receive an answer can be accepted later. Either sender and receiver need to be able to initiate communication and when failures in communication are to be expected.

**Synchronous Communication**

Synchronization can occur at three stages
i) The sender can synchronize till it receive acknowledgement that the middleware will take over transmission or that the message will be stored at the recipient buffer(recipient based)

ii) The sender can synchronize until the receiver has received the intended message(delivery based)

iii) The sender is blocked till it receives acknowledgement that it&#39;s equest has been fully processed by the receiver ie until the sender receives a response.(response-based)

So, in synchronous communication, the sender is blocked until its message is stored by the middleware or at the receiving host or till it receives a response. Synchronous communication is preferred when it is acceptable to block the sender until it receives a response and when the communication network is reliable.

**Asynchronous Communication**

In asynchronous communication, the sender moves on as soon as it is done submitting the message for transmission. Processes are not blocked by other processes that are waiting to be resolved. Consequently, multiple actions can happen at the same time, reducing the wait time for users.
At the same time, response-times are not predictable, affecting time-sensitive applications. Also, errors and service failures are harder to track

_Several combinations of communications are used. Examples are_

- Persistent Asynchronous
- Persistent Synchronous
- Transient Asynchronous
- Receipt-Based Transient Synchronous
- Delivery-Based Transient Synchronous
- Response-Based Transient Synchronous
