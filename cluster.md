---
layout: page
title: Cluster commands
nomenu: true
---

Cluster commands are used to manage a cluster of XFireDB servers. Below
you'll find a descriptive list of all relative commands.

### CLUSTER USERMOD
	CLUSTER USERMOD <username> <action>=arg
Modify a user. Valid actions are:
	* LEVEL: to change the access level. Levels >= 10 are admin.
	* PASS: change the password of a user.
	* USERNAME: change username

### CLUSTER USERADD
	CLUSTER USERADD <username> <password>
Create a new username with standard rights. Use usermod to change the
rights of a user.

### CLUSTER USERDEL
	CLUSTER USERDEL <username>
Delete a user.

### CLUSTER FORGET
	CLUSTER FORGET <id>
Forget a cluster node (i.e. delete the node from the cluster). All keys (and data)
that the node holds will be distributed evenly across all other nodes.

### CLUSTER MIGRATE
	CLUSTER MIGRATE <num> <dst>
Migrate a number of slots from the 'this' node to another node.

### CLUSTER SLOTS
	CLUSTER SLOTS
Get the number of slot distribution of a cluster.

### CLUSTER RESHARD
	CLUSTER RESHARD <number-of-slots> <source-node> <dst-node>
Reshard keyslots between nodes.

### CLUSTER NODES
	CLUSTER NODES
List all the available nodes in a cluster.

### CLUSTER WHEREIS?
	CLUSTER WHEREIS? <key>
Find out on which node a specific key (or will be stored).

### CLUSTER MEET
	CLUSTER MEET <ip> <port> <username> <password>
Add a new node to the cluster. The username and password are the local username/password for that
specific node.

