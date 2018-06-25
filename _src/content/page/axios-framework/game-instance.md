---
title: "Axios Framework Instance"
date: 2018-06-17T21:02:00+02:00
subtitle: "The (fake) class that manages it all"
tags: 
    # - example
bigimg: 
    # - {src: "path", desc: "description"}
comments: true
---
`Instance` is the main class of the framework, you could call it an instance of the framework, but it really is an instance of a game. `Instance` is responsible for managing the render window and guiding the program. It is the main loop of the game
<!--more-->

## Documentation
> Code hosted on Github: [Header](https://github.com/antjowie/Axios-framework/blob/master/include/Axios/Instance.h) and [Source](https://github.com/antjowie/Axios-framework/blob/master/src/Axios/Instance.cpp)

#### Instance
_The `Instance` class manages the whole render window. It has been made a class to work around the fact that SFML does not support open windows to turn to fullscreen._  

## Design choices
#### Game Loop and the importance of time
The `Game Loop` is responsible for updating everything, it is the code that is repeatedly run.  

The `Game Loop` will make sure that the user experiences our game in the same speed as everyone else does. Most of the time, games will run at the fastest speed possible, but with a higher fps, the program runs faster. This means that things like movement will be different.

This is fixed by using a time variable. For perfect results, we need the time the frame is taking and multiply all physics related code with it, but we can't predict the time it will take to render the frame, because the calculations will be finished by then. There are several ways to fix this.

#### Fixing timing 
We could use the time of the previous frame, it is an estimation of the time the next frame will take. If however, something very demanding would happen on that frame, the time would be incorrect, leading to lag. Because the frame took long but the time value is relatively low.  

Another approach is to take the last few frame's time and calculate their average. This would result into a fairly accurate guess and sudden lags would compensate and not make you warp on the next frame. But because this approach uses an average, a game with many demanding and undemanding frames close by would make the game feel sluggish.

In the end, it all depends on your game. I will take the latter approach because my game won't be that demanding and it is the safer choice.

That should conclude the game instance class. If you have any questions or suggestions, leave them in the comments down below. Thank you!

[Return to project page.]({{< ref "projects\axios-framework.md" >}}#what-does-it-do)