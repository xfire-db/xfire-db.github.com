---
layout: page
title: XQL
---

## Communicating with XFireDB

XFireDB uses XQL as its scripting language. Using XQL you can interface with XFireDB in a similar
fashion as XQL does for your every day XQL database. Below are all the available XFireDB commands,
both storage and cluster management commands.

## String commands

	GET
	SET

## [Hashmap commands](/hmap/)

	MDEL
	MREF
	MCLEAR
	MADD
	MSIZE

## Set commands

	SINCLUDE
	SADD
	SDEL
	SCLEAR

## List commands

	LPUSH
	LREF
	LPOP
	LSIZE
	LSET

## General commands

	DELETE

## CLUSTER commands

	CLUSTER USERMOD
	CLUSTER USERADD
	CLUSTER USERDEL
	CLUSTER FORGET
	CLUSTER MIGRATE
	CLUSTER SLOTS
	CLUSTER RESHARD
	CLUSTER NODES
	CLUSTER WHEREIS?
	CLUSTER MEET

