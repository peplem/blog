---
title: "Address Space Made Simple"
date: "2022-11-11"
---

From the book Windows10 system programming, a simple explanation of windows address space. 

![1.png](/stat-assets/02/1.png)

The first 64 KB of virtual address space are unusable. These are traditionally used to catch NULL pointers. Similarly, the upper 64 KB of address space, just before system space starts, are unusable as well. In short, it means the usable address space range is 128 KB less than perhaps expected. For 64-bit processes, this is completely unnoticeable.