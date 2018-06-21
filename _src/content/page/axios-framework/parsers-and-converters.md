---
title: "Parsers and Converters"
date: 2018-06-21T19:57:14+02:00
subtitle: "Passing data around and saving it"
tags: 
    # - example
bigimg: 
    # - {src: "path", desc: "description"}
comments: true
---
Some things just have to be saved. In our case configurations. To make life easier for both of us (computers and humans), data is saved in a special format. There are many formats that we can choose from. But because of my recent studying of Python and Web Development. My preference for [XML](https://www.w3.org/XML/) (which I only used because of Tiled) shifted to [JSON](https://www.json.org/), a much more easier format, IMHO.
<!--more-->

## So many possibilities (almost roping)
This page will mainly explain the reasons why I chose certain libraries. So why did I chose JSON?

**J**ava**S**cript **O**bject **N**otation is such a simple format. It is like one big array. Is consist of key and values, just like our `Data` class. So why not JSON?  
I also find JSON easy to read and thus to edit. XML is also quite easy, but accessing XML is another story (or maybe I should've studied the librarys documentationa bit more). For our purposes, JSON suffies.

I chose the library [JSON for Modern c++](https://nlohmann.github.io/json/). It isn't the fastest parser, but it is really easy to use. Just include one header. And parsing a 20kb text file doesn't take that long either.

[Return to project page]({{< ref "projects\axios-framework.md" >}})