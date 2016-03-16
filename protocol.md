---
layout: page
title: Protocol
---

XFireDB uses a relatively simple text (string) based protocol
for communication between the client and server. Below the protocol
is explained in detail.

Every command, including XQL commands, are terminated by a newline feed. So when sending
an authentication command this is what should be sent to the server (see below for further
details about authentication).

	AUTH <username> <password>\n

### XQL
XQL is the interfacing language used to communicate with an XFireDB server. Documentation
on the XQL commands can be found [here](/xql). In addition to the XQL commands
there are a few extra commands that can, or have to be used to succesfully establish
a connection.

### Authentication
	AUTH <username> <password>
The AUTH command is used to authenicate to a server. In case of a clustered server, the authentication
is cluster wide. This way a user can connect to any node and authenticate succesfully.
For more information on usermanagement, see this [page](/cluster).

### Streaming
	STREAM
By default, the XFireDB server will terminate the connection after replying to an XQL command.
If the client needs the connection to stay open (i.e. the client wants to send more than
one XQL command), the STREAM command must be issued before the first XQL command and
after the the authentication.

### Return codes

### Termination
	quit
The connection can be terminated at any point by the server. The client
library is responsible for the correct handling of such situations. The client
can terminate the connection by sending the

command to the server.

