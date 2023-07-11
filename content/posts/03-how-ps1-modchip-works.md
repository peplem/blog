---
title: "How Ps1 Modchip Works"
date: 2023-03-03T19:38:53+01:00
---

It is interesting, for the sake of knowledge, to analyze how console modchip works. Even if illegal, these modchips allowed a vast community of hackers to “pwn and escalate” the console they were related to. Beside that, analyzing how they work may teach us some useful security notions that we may not be aware of.

## Copy protection

If we take a look back at cartridge-based consoles we can easily notice that those cartridge are pretty difficult to counterfeit. 

Why? Because you’d need to have very specialized equipment to replicate one of those, because you’d need to have a blank and writable cartridge and, obviously, because it’d be expensive to do on a large scale. 

And there’s where CD-R came to the rescue. They were (are) cheap, easy to find and buy but this whole new way of serving digital content in the videogame industry posed a new problem for Sony: ******************************************************************************************how can we protect our intellectual property?****************************************************************************************** 

CD-R were easy to copy, and CD burners were already a thing when the PS1 came out. 

To enforce digital content protection, and to ensure that only licensed developers could develop and distribute a game on the console, Sony added to their disks… a wobble! In the *useful reading* section there is a paper that explains why the wobble is inevitable and why optical lasers fluctuate constantly to read or write data. In this scenario however Sony used to wobble to accomplish two goals.

The aim of the wobble was to encode some sort of information on the disk that allowed the PS1 CD reader to check if the CD-R was original and certified from a licensed developer and also to encode the **********************region code**********************. During the mastering process a specific length wobble was written on disk and if the wobble on copied disk didn’t match the console BIOS then the game would not start. 

This mechanism was very difficult to replicate because this specific wobble could be reproduced only by industrial level CD burner, consumer burners “ignored” that wobble producing invalid disks. 

## ModChips

Modchips are essentially devices that could be soldered directly on the console motherboard to trick the PS1 into reading counterfeit copies. 

Since the PS1 firmware doesn’t look for the wobble directly (this reading is performed by the CD Decoder), but it looks for the encoded informations that this wobble contains, it is easy for a modchip sitting on top of the decoder to inject malicious code and send poisoned data to the CPU to make it pass the checks no matter what’s actually on disks.

![1.png](/stat-assets/03/1.png)

### *Modchips countermeasures*

In the early stages of their development, modchips were sending text to the CPU at the wrong time. Game developers found a way to intercept fake info and terminate the execution by showing an error.

Like in a cat-and-mouse game, hackers updated their modchips to only send data at the right time while sleeping during boot phase.

---

## Useful readings

[https://www.psxdev.net/forum/viewtopic.php?f=70&t=1266](https://www.psxdev.net/forum/viewtopic.php?f=70&t=1266) - reverse engineering the wobble

[https://www.control.lth.se/fileadmin/control/Education/EngineeringProgram/FRTN10/chaghajerdi2008.pdf](https://www.control.lth.se/fileadmin/control/Education/EngineeringProgram/FRTN10/chaghajerdi2008.pdf) - wobble and optic lasers