---
title: glang cgo problem
categories:
  - go
tags:
  - go
---

# CGO problem
background: using wails to develop go app on win10 go environment

## Problem
```sh
cgo: C compiler "gcc" not found: exec: "gcc": executable file not found in %PATH%
```
why got this problem?
- cygwin 
- msys2 mingw64 

Win10 have both cygwin and msys2.
I use cygwin as default environment.
Need change cygwin to msys2.

## uninstall cygwin
[link](https://www.cnblogs.com/onelikeone/p/17291998.html)

## install gcc
```sh
pacman -S --needed base-level-devel mingw-w64-x86_64-toolchain
```


