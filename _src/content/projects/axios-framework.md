---
title: "Axios Framework"
date: 2018-06-16T13:53:09+02:00
subtitle: "The framework that powers all of my 2D games"
tags: 
    - game-development
    - framework
    - cpp
bigimg: 
    # - {src: "path", desc: "description"}
comments: false
---
The Axios framework makes use of [SFML](https://www.sfml-dev.org/). The Axios framework is used for 2D game development. It was actually meant to be a game engine, but I have no experience making a GUI yet, so a framework it is. 
<!--more-->

The framework is supposed to be an all inclusive pack. During the development of my two first games [Runaway]() and [Ray Shaper]() I noticed a certain pattern. Because time was crucial (Ray Shaper was my intake assignment for Breda University, [read more about that here]({{< ref "post\my-journey-towards-nhtv.md" >}}))
> You can follow this project on Github at this [repository](https://github.com/antjowie/axios-framework)

## What does it do
The framework serves a role in the following subjects `(you can click the links to see the progress)`:

-  [**Instance**]({{< ref "page\axios-framework\game-instance.md" >}})
    - [X] Manage (de)initialization of modules
    - [X] Game loop
-  [**Scene manager**]({{< ref "page\axios-framework\scene-manager.md" >}})  
    _Scenes are containers that manage objects and allow object to interact with eachother. It also allows object to easilly make new data during runtime. A scene can be a menu or level, basically everything that the user makes in Tiled._  
    - [ ] One/two frame stack
    - [ ] Dynamic runtime stack
    - [ ] Object updating
    - [ ] Object reference handling
    - [ ] Event handling
-  **Objects**  
    _Objects are the building blocks of the game. Objects are build of components_
    - [ ] Object factory
    - [ ] Animation handling
    - [ ] Collision and Physics
    - [ ] Object serialization
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
    - [ ] Make file containing all Object types
- [**Input handler**]({{< ref "page\axios-framework\input-handler.md" >}})
    - [X] Keyboard and mouse
    - [ ] Controller
- [**Parsers and Converters**]({{< ref "page\axios-framework\parsers-and-converters.md" >}})
    - [X] JSON parser
    - [ ] XML parser
    - [ ] SFML key code converter

Please ask questions about the project in the dedicated subject. 