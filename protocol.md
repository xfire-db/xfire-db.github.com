---
layout: page
title: Protocol
---

XFireDB uses a relatively simple text (string) based protocol
for communication between the client and server. Below the protocol
is explained in detail.

### Authentication

### Return codes

### Termination
The connection can be terminated at any point by the server. The client
library is responsible for the correct handling of such situations. The client
can terminate the connection by sending the

	quit

command to the server.

