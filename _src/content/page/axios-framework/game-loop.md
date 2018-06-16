---
title: "Axios Framework Game Loop"
date: 2018-06-16T13:56:00+02:00
subtitle: "How the Axios framework updates everything"
tags: 
    # - example
bigimg: 
    # - {src: "path", desc: "description"}
---
The `Game Loop` is responsible for updating everything, it is the code that is repeatedly run.  
## What will the Game Loop do
The `Game Loop` will make sure that the user experiences our game in the same speed as everyone else does. Most of the time, games will run at the fastest speed possible, but with a higher fps the program runs faster. This means that things like movement will be different.

This is fixed by using a time variable. For perfect results we need the time the frame is taking and multiply all physics related code with it, but we can't predict the time it will take to render the frame, because the calculations will be finished by then. There are several ways to fix this.

#### Fixing timing 
We could use the time of the previous frame, it is a estimation of the time the next frame will take. If however, something very demanding would happen on that frame, the time would be incorrect, leading into a lag. Because the frame took long but the time value is relatively low.  

Another approach is to take the last few frame's time and calculate their average. This would result into a fairly accurate guess and sudden lags would compensate and not make you warp on the next frame. But because this aproach uses an average, a game with many demanding and non demanding frames close by would make the game feel sluggish.

In the end, it all depends on your game. I will take the latter approach because my game wont be that demanding and it is the safer choice.

#### The loop itself
The game loop will follow the following procedure:
```cpp
Average<Time,20> averageTime; // 20 is the amount of elements to hold
Clock frameTime;    // A class that keeps track of the time elapsed between reset calls
Time elapsedTime;
const float refreshRate = 60;
elapsedTime = frameTime.reset();

while (gameIsRunning)
{
    // If the game has an fps lower than 0, skip the frame
    if (elapsedTime.ms() > 1)
    {
        elapsedTime = 0;
        continue;
    }

    gs_inputHandler::updatePressed();
    // This unties our input polling rate from our rendering,
    if (1.f/elapsedTime.ms() >= refreshRate)
    {
        averageTime.push(elapsedTime.ms());
        elapsedTime %= 1.f/refreshRate;

        updateScene(averageTime.getAverage());
        renderScreen();

        gs_inputHandler::updateReleased();
        /*
        The input handler handles three different types of input
        pressed,hold,released.
        We can't set these states to false in our input loop because it runs faster
        than our render loop. When the user presses a button, he expects to see it
        happen in the program. 
        You could also tie the input handler to the rendering loop, but the input could
        skip a frame and end up at the next frame. If the user would press a key and 
        release it inbetween the frame (when the program is waiting until enough time has passed
        for the next frame), it could not be registered. Of course, this will only happen at low fps. 
        Something that isn't supposed to happen in our game, but this way the risk will be dodged. 
        */
    }
    elapsedTime += frameTime.reset();
}
```
Everything should make sense, the code itself is very simple. But the game loop class isn't a complicated class. All it has to do is make sure that everything is updated with the correct timings. For now, I think this is all the game loop needs