---
layout: page
title: Compiling
---

XFireDB supports a lazy compilation process. This means the most
popular systems can be built with a relatively simple command. The
root Make file is able to take several, all non-mandatory, arguments:

* TARGET = [host | win32 | win64]
* DEBUG = [true | false]
* CLIENTS = [true | false]
* SERVER = [true | false]
* X64 = [true | false]
* RBCONF = [true | false]

An important to note that CMake is unable to detect the correct Ruby configuration
file when cross compiling for Windows. When you want to cross compile for Windows, you
need to

a) download mingw (32 or 64 bit)
b) download and cross compile OpenSSL
c) download and cross compile ruby
d) provide XFireDB with a valid ruby configuration

Configuring OpenSSL for Windows can be done as following:

32-bit:
	CROSS_COMPILE="i686-w64-mingw32-" ./Configure mingw no-asm shared --prefix=/opt/mingw32
64-bit:
	CROSS_COMPILE="x86_64-w64-mingw32-" ./Configure mingw64 no-asm shared --prefix=/opt/mingw64

Configuring ruby:
	gem install rake-compiler
	rake-compiler cross-ruby HOST=mingw32
	rake-compiler cross-ruby HOST=mingw64

The XFireDB RBCONF argument can then be used to crosscompile XFireDB:
	make DEBUG=false TARGET=win64 RBCONF=~/.rake-compiler/ruby/x86_64-w64-mingw32/ruby-2.1.5/lib/ruby/2.1.0/i386-mingw32/rbconfig.rb
