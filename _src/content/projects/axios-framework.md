---
title: "Axios Framework"
date: 2018-06-16T13:53:09+02:00
subtitle: "The framework that powers all of my 2D games"
tags: 
    - game-development
    - framework
    - cpp
    - sfml
bigimg: 
    # - {src: "path", desc: "description"}
comments: false
---
The Axios Framework makes use of [SFML](https://www.sfml-dev.org/). The Axios Framework is a 2D game framework that runs on files made by [Tiled](https://www.mapeditor.org/). The programmer only writes the objects. The objects are exported to a file that can be loaded in [Tiled](https://www.mapeditor.org/), a 2D tilemap editor. At first, I wanted to make a game engine, but I have no experience making any kind of GUI yet. I believe that you should not do two major new subjects at the same time, so a framework it is. Hopefully, this project can one day evolve into a game engine.
<!--more-->

## My motivation for this project
The framework is supposed to be an all inclusive pack. During the development of my two first games [Runaway](https://github.com/antjowie/Runaway) and [Ray Shaper](https://github.com/antjowie/Ray-Shaper), I noticed a certain pattern. Time was crucial (Ray Shaper was my intake assignment for Breda University, [read more about that here]({{< ref "post\my-journey-towards-nhtv.md" >}})) so I copied and pasted much of the code from Runaway. Many of those files were modified to meet certain needs, but the animation files and the game loop stayed the same.  
Most of the time when I'm programming and come up with a new idea, I first prototype that idea, then make some throwaway code to test it and see if its something to implement. Because of my limited time, all the prototype and throwaway code came into the final product. Optimization was my last priority, which is why that simple game lagged in its final stage. Everything just had to work. But I had no base code to start with. Only another prototyped project.

So with that knowledge and some extensive reading of the book [Game Engine Architecture](http://gameenginebook.com/), the Axios Framework started to become my next project. 

> The source code for this project is hosted on Github at this [repository](https://github.com/antjowie/axios-framework).

___
## What does it do
The framework serves a role in the following subjects. The subjects are their responsibilities. Marked subjects are being worked on. Unmarked subjects aren't. `(you can click the bold title to see the progress)`:

-  [**Instance**]({{< ref "page\axios-framework\game-instance.md" >}})  
    __The `Instance` class is an instance of the framework. It updates all the systems. The `Instance` class manages the update loops._  
    - [X] Manage (de)initialization of subsystems
    - [X] Frame rate control
-  [**Object manager**]({{< ref "page\axios-framework\object-manager.md" >}})  
    _The `Object manager` is a container that manages the memory/allocation/lifetime of all the `Objects` and allows `Objects` to be querried. It also allows `Objects` to easilly initiate data during runtime._  
    - [X] One/two frame stack
    - [X] Runtime object (de)allocation
    - [X] Object reference handling
    - [X] Physics update loop
    - [ ] Event system
    - [ ] Object serialization
-  **Objects**  
    _Objects are the building blocks of the game. Objects are build out of hooks to subsystems._  
    - [ ] Object factory
    - [ ] Object serialization
-  **Subsystems**  
    _Subsystems are systems that objects can make hooks to. Subsystems make hooks to an update loop of the `Instane` class. This allows the programmer to easily make his own subsystem._  
    - [ ] Subsystem foundation
    - [ ] Animation subsystem
    - [ ] Rigid body (collision response/physics) subsystem
- [**Data manager**]({{< ref "page\axios-framework\data-manager.md" >}})  
    _Basic data containers for game data that has to be saved._
    - [X] Game keybinding items
    - [X] User config
- **Assets manager**  
    _Keeps the game textures, sounds, files in memory to which objects can make reference too._
    - [ ] Sound
    - [ ] Music
    - [ ] Textures
    - [ ] Fonts
- **Tiled support**  
    _[Tiled](https://www.mapeditor.org/) will be used as the editor._
    - [ ] Import Tiled files
    - [ ] Export object data type
- [**Input handler**]({{< ref "page\axios-framework\input-handler.md" >}})  
    _An interface that keeps track of all input devices and their state._
    - [X] Keyboard and mouse
    - [ ] Controller
- [**Utilities**]({{< ref "page\axios-framework\utilities.md" >}})  
    _Code that allows communication with other programs or supports the developer during development._
    - [X] JSON parser
    - [ ] SFML key code converter
    - [X] Logger
    - [ ] String hashing

___
Please ask questions about the project in the dedicated subject. 