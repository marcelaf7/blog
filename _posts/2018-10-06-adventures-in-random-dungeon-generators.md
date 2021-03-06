---
layout: post
title:  "Adventure In Random Dungeon Generators"
---

There have been a few connecting ideas that I have been fiddling with and thinking about for a while. The first one is the idea of browser games coded only with HTML, CSS, and JavaScript. The second is roguelike games which brought me to the third, random generators (specifically a dungeon generator). So I decided to work on a project that does all 3 of those things. The public repository for the project is [HTML-Game](https://github.com/marcelaf7/HTML-Game) on my GitHub account.

I mentioned this post earlier on my first ever blog post, [Introduction](http://marcelfiore.com/blog/2018/10/03/introduction.html). It was this project that inspired me to start this blog and I actually wrote most of this post in the notes of my phone before I actually started the blog. I figured this blog deserved an introductory post explaining what kind of posts would be here and why I started it before I made this post.

Back to the topic at hand, I already did some work on the project. I started the basic UI; a simple hard-coded grid of pixel art images. The JavaScript code changes the image that displays on the grid depending on what item is in that space of the game. I also did basic player movements. I have not gotten to obstacle handling yet, but I am prioritizing the generator because it is a new topic and I am anxious to start.

Right now, I am focusing on the dungeon map. I want it to be randomly generated, but I have never actually dealt with random generation before - other than the occasional random number. I spent a lot of time researching random generators and noise algorithms. I eventually stumbled upon a Reddit post about how random terrain generators for games work and was linked to a blog post by Notch, the creator of Minecraft. He explains how the terrain generator works and how it changed over time. Every iteration used [Perlin Noise](https://en.wikipedia.org/wiki/Perlin_noise) in some way to achieve the terrain generator.

I did a lot of reading about Perlin Noise and how it worked. I spent a few hours trying to use it in my dungeon generator, but I eventually decided not to use it. I did so, partially because the code examples I found online for Perlin Noise were really hard to follow, but mostly because Perlin Noise makes round, smooth shapes. My plan for this game is for the dungeons to be filled with rectangular rooms rather than rounded openings.

So I came up with a new, simpler idea. I could just write an algorithm that generates random rectangles for rooms and draws lines between them for hallways or passageways. So far, it is going even better than I expected. Generating random rectangles that can overlap creates mostly rectangular rooms and occasional odd shaped ones. It also creates a wider range of room sizes. At the time of writing this post, I have the rectangle generator done, but I have yet to finish the code for the hallways. I have high hopes and I trust that it will go well. I will post an update on the final product in a future post.

Here's what the generator looks like so far:

![dungeon generator image](/blog/images/2018-10-06-dungeon-generator.png)
