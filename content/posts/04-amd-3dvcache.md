---
title: "How does AMD 3D-VCache work"
date: 2023-07-08T18:00:00+02:00
draft: false
---

# Inter chip connection

![c4_tech.png](/stat-assets/04/c4_tech.png)

Chip inter-connection technologies are adoperated to connect two chips together allowing them to operate together. The number of “connecting points” is different from one technology to another. Starting with the less-dense C4 (controlled collapse chip connection), some vendors moved to a more dense technique called **Micro Bump**. In this second scenario you can easily notice that the dots representing the inter-chip connections are much more dense. 

AMD 3D V-Cache is implemented with a new approach: **Hybrid Bond 3D.** This approach offers better connectivity (the dots are much more dense with respect to the previous scenarios), which automatically translates in more data flowing between chip in the same amount of time. 

# Stacking problems

CPU dies, heatspreader and CPU coolers are designed with standard dimensions. This means that the height of the actual CPU die is designed to allow a perfect fit of the heatspreader and, on top of it, a perfect fit of the CPU cooler. 

![die_thinning.png](/stat-assets/04/die_thinning.png)

Now, let’s consider the height of a standard Zen3 die (pink one), let’s call it **z:**  this height is the standard height described earlier in this paragraph. When a new chip is stacked on top of the die the height is not **z** anymore. 

This is a problem. 

Now heatspreader have to be re-designed, CPU cooler are not going to fit anymore on the same socket and this is not good either. To avoid this, AMD solved this problem by making the actual Zen3 die thinner (green one). This means that with the same height **z** the die has now an additional chip on top of it. Great! No coolers or heatspreaders have to be redesigned. 

# Molecular perfection

Chips are now stacked together. Nice. That’s exactly what AMD was looking for, but how does this new unit (die + stacked chip) stays together? What prevents them from falling apart?

Well, physics comes to rescue: when you have two surfaces which are **perfectly flat and smooth,** if you bring them together they will bond together forming a new cohesive unit. That’s what **Van Der Waals forces** are. And that’s it! 

# Why 3D V-Cache is so fast in games?

Videogames, from the computer perspective, are full of randomness. What does it mean? It means that the computer **can’t predict what the player is going to do**. Movements, enemies showing up, interactions, environmental changes are all random action that the player is - most of the time - in control of and that the computer has no way to predict. Each of these actions means new animations, texture to be loaded, etc.

Where are those information collected from? CPU cache! But CPU cache is insanely fast if compared to RAM and it is also orders of magnitude smaller (L3 Cache is in MB, while RAM is in GB). 

The access time of the CPU cache is ~8-10 nanoseconds, while RAM access time is tipically ~10 times slower that that, hence, fetching data from RAM is slower with respect to fetching data from CPU cache. Here’s where the magic happens. 

More data can be fetched from CPU cache, which means that the CPU can get more data in the same amount of time, which means low latency in terms of data elaboration, which means performance or **frames per second**. And that’s why a CPU with 3D V-Cache has an average gain, in 1080p, of **15%.** This is insane. A gain like this is like going from Zen2 to Zen3, except for the fact that 3D V-Cache is not a new architecture. It’s just memory. 

### Useful resources

Van Der Waals forces: [https://en.wikipedia.org/wiki/Van_der_Waals_force](https://en.wikipedia.org/wiki/Van_der_Waals_force)

Reference for this post: [https://www.amd.com/en/technologies/3d-v-cache](https://www.amd.com/en/technologies/3d-v-cache)