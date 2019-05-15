---
layout: default
title: Passing Reference Parameters In Remote Procedural Calls
---

# Passing Reference Parameters In Remote Procedural Calls

**Challenges to passing Reference parameters in RPC**

_Forbid pointers and reference Parameters_

Call-by-reference is not possible as the client and server don&#39;t share an address space._
  Passing a reference parameter as such to the remote server means nothing as the address being referred to by the client is an address of the client .For this reason, passing reference values is generally avoided.

_call-by-copy/restore_

However, call by reference can be implemented by using copy/restore. The values in the referenced address in the client are copied and sent across the network. The server stub then unpacks them and makes a call to the function residing in the server. The returned values are then sent back over the network and copied into the original referenced address overriding the original values

_Copy-restore_

It  works similarly to call-by-reference. However, it does not work in all cases._ For instance, if the same argument is passed twice, two copies will be made, and references through one parameter changes only one of the copies.

_One-Optimization_

If the values(to be sent) being accessed through reference parameters are only input parameters to the function in remote server, they do not need to be copied back to the referenced address. Similarly, if the value are only output parameters, then they do not need to be copied to the server

Presently call-by-reference can he handled for simple structures and arrays._​ Even if the RPC supports more complex structures such as trees, the values would have to be copied and sent over in a pointer-less structure such as flattened trees and be reconstructed again in the remote server.
