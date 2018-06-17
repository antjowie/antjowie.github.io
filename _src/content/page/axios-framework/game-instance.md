---
title: "Axios Framework Game Instance"
date: 2018-06-17T21:02:00+02:00
subtitle: "The class that manages it all"
tags: 
    # - example
bigimg: 
    # - {src: "path", desc: "description"}
---
The `Game Instance` is the main class of the framework, you could call it an instance of the framework, but it really is an instance of a game. The `Game Instance` is responsible for managing the game settings. All the user configurations (keybindings, resolution, audio) and the data path (path to the game assets) will be managed by the `Game Instance`.
<!--more-->

# Table of Contents
- [Code](#code)
- [Input handler loop](#input-handler-loop)
- [Game loop](#game-loop)

## Code
{{< highlight cpp "linenos=inline,hl_lines=1 18" >}}
// GameInstance.h
#pragma once

namespace ax
{
    namespace GameInstance
    {    
        // Starts the game loop
        void start();

        // Initialize all modules
        void init();
    }
}



// GameInstance.cpp
// Spacing between # and include is because of formatting errors
# include "GameInstance.h" 
# include "InputHandler.h"

# include <SFML/System/Clock.h>
# include <SFML/System/Time.h>
# include <SFML/System/Event.h>
# include <SFML/Graphics/RenderWindow.h>

void ax::GameInstance::start()
{
    Average<float,20> averageTime; // 20 is the amount of elements to hold. Average 
                                  // is a class queue like class with a max size of
                                  // 20. It can return the average of all its elements
    Clock frameTime; // A class that keeps track of the time elapsed between reset calls
    sf::RenderWindow window(
        sf::VideoMode(ax::DataManager::Config["windowX"],ax::DataManager::Config["windowY"]), 
        ax::DataManager::Config["title"]);
    sf::Event event;
    Time elapsedTime;
    elapsedTime = frameTime.reset();

    while(window.isOpen())
    {
        // If the game has an fps lower than 0, skip the frame
        if (elapsedTime.ms() > 1)
        {
            elapsedTime = 0;
            continue;
        }

        ax::InputHandler.update();
        // Event handling should be done in the game loop because if the
        // events will be polled elsewhere, the events can be skipped
        while(window.pollEvent(event))
        {
            switch(event.type)
            {
                // Convert key code to key string
                // Keyboard and mouse handling
                case sf::Event::Keyboard::isKeyPressed:
                    ax::InputHandler::updatePressedKey(event.key); 
                    break;
                case sf::Event::Keyboard::isKeyReleased:
                    ax::InputHandler::updateReleasedKey(event.key); 
                    break;
                case sf::Event::Mouse::isButtonPressed:
                    ax::InputHandler::updatePressedButton(event.button); 
                    break;
                case sf::Event::Mouse::isButtonReleased:
                    ax::InputHandler::updateReleasedbutton(event.button); 
                    break;

                // TODO Add joystick support

                case sf::Event::Closed:
                    window.close();
                    break;
            }
        }
        
        // This unties our input polling rate from our rendering,
        if (1.f/elapsedTime.ms() >= ax::DataManager::Config["refreshRate"])
        {
            averageTime.push(elapsedTime.ms());
            elapsedTime %= 1.f/ax::DataManager::Config["refreshRate"];

            updateScene(averageTime.getAverage());
            renderScreen();
        }
        elapsedTime += frameTime.reset();
    }
}

void ax::GameInstance::init(){
    // Write some code to parse config file(JSON parser)
    // Init ax::DataManager::Config with correct data
    // Init ax::InputHandler with correct data
}
{{< / highlight >}}

## Input handler loop
Input items have three states, `pressed`, `hold`, `released`. The program checks if a key is pressed and will check if the `hold state` is **true**. If the `hold state` is **true**, the `hold state` will remain **true**. If the `hold state` is **false**, the `hold state` and `pressed state` will turn **true**.  After every frame, the `pressed state` and `released state` will become **false**. If a key is released, the `release state` will become **true** and `all other states` will become **false**.

To summarize default flow (every column is a frame):

| Situation         | Pressed | Hold | Released |
| ----------------- | ------- | ---- | -------- |
| Pressing key      | X       | X    |          |
| Holding the key   |         | X    |          |
| Holding the key   |         | X    |          |
| Releasing the key |         |      | X        |

## Game Loop
The `Game Loop` is responsible for updating everything, it is the code that is repeatedly run.  

The `Game Loop` will make sure that the user experiences our game in the same speed as everyone else does. Most of the time, games will run at the fastest speed possible, but with a higher fps, the program runs faster. This means that things like movement will be different.

This is fixed by using a time variable. For perfect results, we need the time the frame is taking and multiply all physics related code with it, but we can't predict the time it will take to render the frame, because the calculations will be finished by then. There are several ways to fix this.

#### Fixing timing 
We could use the time of the previous frame, it is an estimation of the time the next frame will take. If however, something very demanding would happen on that frame, the time would be incorrect, leading to lag. Because the frame took long but the time value is relatively low.  

Another approach is to take the last few frame's time and calculate their average. This would result into a fairly accurate guess and sudden lags would compensate and not make you warp on the next frame. But because this approach uses an average, a game with many demanding and undemanding frames close by would make the game feel sluggish.

In the end, it all depends on your game. I will take the latter approach because my game won't be that demanding and it is the safer choice.

That should conclude the game instance class. If you have any questions or suggestions, leave them in the comments down below. Thank you!

[Return to project page]({{< ref "projects\axios-framework.md" >}})