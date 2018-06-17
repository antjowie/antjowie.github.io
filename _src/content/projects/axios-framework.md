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
---
The Axios framework makes use of [SFML](https://www.sfml-dev.org/). The Axios framework is used for 2D game development. It was actually meant to be a game engine, but I have no experience making a GUI yet, so a framework it is. 
<!--more-->

> You can follow this project on Github at this [repository](https://github.com/antjowie/axios-framework)

## What does it do
The framework serves a role in the following subjects `(you can click the links to see the progress)`:

- [ ] [`Game instance`]({{< ref "page\axios-framework\game-instance.md" >}})
    - [ ] Manage user settings
    - [ ] Manage (de)initialization of modules
    - [ ] Game loop
- [ ] `Scene manager`  
    _Scenes are containers that contain objects and sometimes static level data. A section can be the main menu, level, options menu, loading screen etc_  
    - [ ] One frame stack
    - [ ] Dynamic object management (add and remove objects during runtime)
    - [ ] Object updating
    - [ ] Object references 
    - [ ] Event handling
- [ ] `Objects`  
    _Objects are the building blocks of the game. Objects are build of components_
    - [ ] Object factory
    - [ ] Animation handling
    - [ ] Collision and Physics
    - [ ] Object serialization
- [ ] `Data manager`  
    _Basic data containers for game data that has to be saved_
    - [ ] Sound
    - [ ] Music
    - [ ] Images
    - [ ] Fonts
    - [ ] User config
    - [ ] Asynchronous
- [ ] `String hashing (will probably be done by another library)`
- [ ] `Tiled support`  
    _[Tiled](https://www.mapeditor.org/) will be used as the main editor for scenes. With Tiled, all scenes initial state will be made._
- [ ] `Input handler`
    - [ ] Keyboard and mouse
    - [ ] Controller
- [ ] `Parsers and Converters`
    - [ ] JSON parser
    - [ ] XML parser
    - [ ] SFML key code converter
- [ ] `Specialized containers`
    - [ ] Average