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
The Axios framework makes use of [SFML](https://www.sfml-dev.org/). The Axios framework is used for 2D game development. It was actually meant to be a game engine, but I have no experience making a GUI yet. I believe that you should not do two major new subjects at the same time, so a framework it is. 
<!--more-->

The framework is supposed to be an all inclusive pack. During the development of my two first games [Runaway](https://github.com/antjowie/Runaway) and [Ray Shaper](https://github.com/antjowie/Ray-Shaper) I noticed a certain pattern. Time was crucial (Ray Shaper was my intake assignment for Breda University, [read more about that here]({{< ref "post\my-journey-towards-nhtv.md" >}})) so I copied and pasted much of the code from Runaway. Many of those files were modified to meet certain needs, but the animation files and the game loop stayed the same. With that knowledge and some extensive reading of the book [Game Engine Architecture](http://gameenginebook.com/), the Axios framework started to become my next project. 

> You can follow this project on Github at this [repository](https://github.com/antjowie/axios-framework)

## What does it do
The framework serves a role in the following subjects. Marked subject have a solid idea. Unmarked subjects have yet to take any shape. `(you can click the bold title to see the progress)`:

-  [**Instance**]({{< ref "page\axios-framework\game-instance.md" >}})
    - [X] Manage (de)initialization of modules
    - [X] Game loop
    - [X] Workaround to make window fullscreen during runtime
-  [**Scene manager**]({{< ref "page\axios-framework\scene-manager.md" >}})  
    _Scenes are containers that manage objects and allow object to interact with eachother. It also allows object to easilly make new data during runtime. A scene can be a menu or level, basically everything that the user makes in Tiled._  
    - [X] One/two frame stack
    - [X] Dynamic runtime stack
    - [X] Object updating
    - [X] Object reference handling
    - [ ] Event handling
-  **Objects**  
    _Objects are the building blocks of the game. Objects are build of components_
    - [ ] Object factory
    - [ ] Animation handling
    - [ ] Collision and Physics
    - [ ] Object serialization
-  **Subsystems**  
    _Subsystems are systems that classes can make hooks to. They are updated in every scene. The reason why subsystems are not in the objects is because this way couping between subsystems and objects is not present_
    - [ ] Animation
    - [ ] Rigid body (collision response/physics)
- [**Data manager**]({{< ref "page\axios-framework\data-manager.md" >}})  
    _Basic data containers for game data that has to be saved_
    - [X] Game keybinding items
    - [X] User config
- **Assets manager**  
    _Game textures, sounds, files that are static and are different depending on the scene._
    - [ ] Sound
    - [ ] Music
    - [ ] Images
    - [ ] Fonts
    - [ ] Asynchronous scene transition
- **Tiled support**  
    _[Tiled](https://www.mapeditor.org/) will be used as the main editor for scenes. With Tiled, all scenes initial state will be made._
    - [ ] Load external map
    - [ ] Export Object types
- [**Input handler**]({{< ref "page\axios-framework\input-handler.md" >}})
    - [X] Keyboard and mouse
    - [ ] Controller
- [**Utilities**]({{< ref "page\axios-framework\utilities.md" >}})
    - [X] JSON parser
    - [ ] SFML key code converter
    - [X] Logger

Please ask questions about the project in the dedicated subject. 