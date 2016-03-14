---
layout: page
title: Hashmap commands
nomenu: true
---

Hashmap commands are used to manipulate hashmaps in XFireDB. Below you'll
find a descriptive list of all available related commands.

### MDEL
	MDEL <key> <hashkey1> <hashkey2> ...
Delete a key from a hashmap.

### MREF
	MREF <key> <hashkey1> <hashkey2> ...
Reference one or more keys within a hashmap.

### MCLEAR
	MCLEAR <key>
Clear out an entire hashmap.

### MADD
	MADD <key> <hash-key> <data>
Add a new entry to a hashmap.

### MSIZE
	MSIZE <key>
Get the size of a hashmap (number of entry's).

### DELETE <key>
	DELETE <key>
Delete the given key.

