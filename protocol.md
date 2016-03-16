---
layout: page
title: Protocol
---

XFireDB uses a relatively simple text (string) based protocol
for communication between the client and server. Below the protocol
is explained in detail.

Every command, including XQL commands, are terminated by a newline feed. So when sending
an authentication command this is what should be sent to the server (see below for further
details about authentication). Reply's from the server are newline terminated too.

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

The server will reply with "OK" in case of a succesfully authentication, when the
authentication failed, "Access denied" will be replied. Please not that these return
value's are NOT preceded by either a byte count, or return code.

### Streaming
	STREAM
By default, the XFireDB server will terminate the connection after replying to an XQL command.
If the client needs the connection to stay open (i.e. the client wants to send more than
one XQL command), the STREAM command must be issued before the first XQL command and
after the the authentication. The stream command will not be acknowledged by the server.

### Return codes
When the server reply's to a command, it will not sent the return value straight out. Before
sending the return value, the number of bytes of the return value are sent (INCLUDING the newline
terminator).

	xfiredb> LREF tl 0..-1
	> 4 5 6
	> +hi
	> +hey
	> +hey!

As per the example above, the byte counts for all 3 reply's (of the same command) are sent in one reply,
seperated by spaces.

The + sign at the start of the data reply's are a return code. The following return codes are
used by XFireDB:

* + (for a string reply's)
* % (for integer reply's)
* & (for boolean reply's)
* - (for status reply's)

Possible status reply's are "OK" and "nil". "nil" is returned, for example, when a requested key
does not exist.

### Termination
	quit
The connection can be terminated at any point by the server. The client
library is responsible for the correct handling of such situations. The client
can terminate the connection by sending the

command to the server.

