---
layout: page
title: List commands
nomenu: true
---

List commands can be used to manipulate lists in XFireDB. Below you'll
find a descriptive list of all relative commands.

### LPUSH
	LPUSH <key> <data>
Push data into a list.

### LREF
	LREF <key> <idx | range>
Reference a list by index or range. The index and range are both zero counted. Negative
ranges (i.e. 0..-1) can be used to reference from the tail of the list.

### LPOP
	LPOP <key> <idx | range>
Pop data from a list by index or range.

### LSIZE
	LSIZE <key>
Get the size (i.e. number of elements) of a list.

### LSET
	LSET <key> <idx> <data>
Set the data at a specific index of a list.

### LCLEAR
	LCLEAR <key>
Clear all entry's from a list.

