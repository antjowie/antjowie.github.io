---
title: "Data Manager"
date: 2018-06-19T18:20:16+02:00
subtitle: "I need some way to keep track of everything"
tags: 
    # - example
bigimg: 
    # - {src: "path", desc: "description"}
comments: true
---
The `Data Manager` is responsible for the data. This is not to be confused with the `Assets Manager` which is responsible for all the assets. The data are all the configurations. Keybindings, resolution, everything that has a string or integer attached to it. It acutally is a map.
<!--more-->

## Documentation
#### Data Manager
_Can also be a class. Holds two instances of Data_

#### Data
_The Data class is a wrapper around an unordered map. It support serialization and checking_

- `Functions`
- **void check(name, value, force)**  
Check a certain value. If force is true, force the change, else change only if it doesn't exist.
- **void check(force)**  
Check the whole map, used before starting the game to see if every config item exists.
- **load/save**
Loads a JSON file or dumps to a JSON file. JSON files are parsed with the library [JSON for Modern C++](https://nlohmann.github.io/json/).

## Additional notes
The reason why `Data Manager` and `Assets Manager` are seperated from eachother, is because the Data can be changed by the user. Assets are not supposed to be changed by the user. Assets do however, keep changing, atleast the content in `Assets Manager`. This means that the `Assets Manager` class will support asynchronios loading of assets, or some second buffer that is supposed to be swapped when changing ` Scenes`. Data does not play a part in this. That is why I have split the two up in different classes.

Suggestions or questions can be written down below as always.

[Return to project page]({{< ref "projects\axios-framework.md" >}})
