---
layout: post
title:  "The Working Dungeon Generator (And Some Issues)"
---

A little over a month ago, I made a post about a random dungeon generator I was trying to figure out. I did it. It probably should not have taken me a full month to complete it, but I had to keep up with my classes and focus on a few other things. Here is a screenshot of one example dungeon:

![working dungeon generator image](/blog/images/2018-11-14-working-dungeon-generator.png)

I am proud that I got it done. It works pretty well and even a little better than I expected. I can imagine this being a generator for a complete game. Naturally, however, I am my biggest critic so there are a few things I am not completely happy with. I want to take the time to explain how the generator works, what went right, a few problems, and how to fix those problems.

## How it works

Here's a somewhat simplified explanation of how it works:

First, it creates the rooms. It randomly generates the first coordinate, then the second (within 10 spaces of the first coordinate). It repeats this until all the rooms are done.

Then it generates the hallways. It chooses two rooms, one that does not have a hallway to/from it yet, and one that already does have a hallway. A random coordinate is chosen from inside each room and a hallway is drawn between them. First by drawing it horizontally then vertically.

This algorithm ended up being a lot simpler than I expected. Every random generation is done just with the Math.random, JavaScript's random number generator.

## Some Things That Went Right

There are a few things I really like about the algorithm. First of all, it works. I am not really surprised that it works, but before I started this project, I knew very little about random generation. I learned a little bit about noise algorithms, I learned a little about how random number generators work, and I had an idea for a new algorithm, coded it, and it worked. I am proud of that.

Next, I like that the rooms of the dungeon are mostly rectangular. I mentioned in the previous blog post that I did not like how some noise algorithms generate mostly circular blobs. I like that this way, the rooms are mostly rectangular, but allowing them to overlap can occasionally create rooms with odd shapes. That was exactly what I wanted, but this also causes a problem that I will explain later.

Additionally, 

## A Few Problems

As with all code, there are a few problems.

The first problem, is that there are very few constraints on the randomness. This is pretty big. It means that even though it is statically unlikely, some bad things could happen. For example, every room could be on the exact same spot, they could all be on one side together, or they could all be close enough that the dungeon is one big room with no hallways. Some of these cases are not all bad, but the problem is that the generator is unpredictable. There aren't any constraints to gaurantee that every random dungeon is full and spread out.

The next problem is that the hallways can do some weird things. These issues are a little more common than the issues with the rooms. A few hallways can line up right next to eachother making an extra wide hallway and sometimes two hallways one space apart. Also, a hallway can go completely through a room while going from one room to another, or when two rooms are connected to make one large room, a hallway can go from one part of the room to another. Most of these issues are not bad, they can create some interesting weirdness, but when these things happen and happen a lot in one dungeon, the dungeon does not look like rooms with hallways, but instead a big blob.

## How To Fix The Problems



