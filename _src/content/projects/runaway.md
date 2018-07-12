---
title: "Runaway"
date: 2017-10-02T17:39:32+00:00
subtitle: "My first game, that was not suppposed to be a game"
tags: 
    - cpp
    - game-development
    - sfml
bigimg: 
    - {src: "/img/runaway/Light-test-1.png", desc: "Working with light"}
    - {src: "/img/runaway/Ligth-example.png", desc: "A broad idea"}
    - {src: "/img/runaway/playerSpritesheet.png", desc: "Making the player move"}
comments: false
---

{{< gallery caption-effect="fade" >}}
  {{< figure link="/img/runaway/Light-test-1.png" caption="Working with light" alt="Light is a very important aspect in this game" >}}
  {{< figure link="/img/runaway/Ligth-example.png" caption="A broad idea" alt="You have to start somewhere" >}}
  {{< figure link="/img/runaway/playerSpritesheet.png" caption="Make him move" alt="How do we process this spritesheet?" >}}
{{< /gallery >}}

Runaway is my attempt to make a simple 2D game which features a basic move set. My main reason for making this game is to see how far I&#8217;ve gotten with my programming skills.
<!--more-->
 I&#8217;m making this game before reading the book <a href="http://www.gameenginebook.com/" target="_blank" rel="noopener">Game Engine Architecture</a>. After I&#8217;ve finished this game, I will read the book. This way, I&#8217;ll see how much my programming skills have improved after reading the book. It seemed like an interesting thing to compare, my skill before and after reading. The most important thing to remember about this project is that game design was not taken into consideration while working on this project. The only reason as for why I started this project, is to get a rough idea of my skill set and understanding of 2D game programming.

The GitHub link for this project can be found [here][1].

## Parts

### Implementing collision with static blocks

[Collision with static blocks part 1][2]. This part discusses how I&#8217;m implementing the functions necessary to not fall through solid blocks.
  
[Collision with static blocks part 1.1][3]. This part continues the previous discussion because there was a flaw with the implementation.
  
[Collision with static blocks part 2][4]. This part explains the implementation of the collision function for all the directions.

### Implementing animation and sprite sheets

[Animation and sprite sheet part 1][5]. This part discusses which tools I use for my sprite sheet and animation creation.
  
[Animation and sprite sheet part 2][6]. This part discusses my implementation of an animation handler class.
  
[Animation and sprite sheet part 2.1][7]. This part discusses how I fixed the bug seen in the video in the previous part.
  
[Animation and sprite sheet part 2.2][8]. This part discusses why our character doesn&#8217;t spawn at the right place.

### Implementing movement

[Movement of player part 1][9]. This part discusses how I&#8217;m implementing the move set.
  
[Movement of player part 2][10]. This part discusses my (odd) implementation of acceleration for movement
  
[Movement of player part 3][11]. I really like this part because it involves making up a formula. In this part, I will discuss how I devised a formula which allows the player to jump to a specific block height.

### Implementing light

[Light part 1][12]. It is time to add one of the gameplay elements into the game. Your lifeline, your light. Of course, every time we wander into a new subject, we must be sure to be fully prepared.
  
[Light part 1.1][13]. Time to fix our gates. While we do have achieved our desired results, the gate class doesn&#8217;t want to work with us. Perhaps it is time to fix the workaround? Yes ,it is.

 [1]: https://github.com/antjowie/Runaway
 [2]:  {{< ref "page\runaway\collision-with-static-blocks-part-1.md" >}}
 [3]:  {{< ref "page\runaway\collision-with-static-blocks-part-1-1.md" >}}
 [4]:  {{< ref "page\runaway\collision-with-static-blocks-part-2.md" >}}
 [5]:  {{< ref "page\runaway\animation-and-sprite-sheet-part-1.md" >}}
 [6]:  {{< ref "page\runaway\animation-and-sprite-sheet-part-2.md" >}}
 [7]:  {{< ref "page\runaway\animation-and-sprite-sheet-part-2-1.md" >}}
 [8]:  {{< ref "page\runaway\animation-and-sprite-sheet-part-2-2.md" >}}
 [9]:  {{< ref "page\runaway\movement-of-player-part-1.md" >}}
 [10]: {{< ref "page\runaway\movement-of-player-part-2.md" >}}
 [11]: {{< ref "page\runaway\movement-of-player-part-3.md" >}}
 [12]: {{< ref "page\runaway\light-part-1.md" >}}
 [13]: {{< ref "page\runaway\light-part-1-1.md" >}}