---
layout:     post
title:      Visual Studio Code
subtitle:   学习笔记
date:       2019-08-29
author:     fzerob
header-img: img/post-bg-python.JPG
catalog: true
tags:
    - python
    - 学习笔记
    - Visual Studio Code (Windows)
---

> About how to use VSCode. Focus on python

## Sourse

youtube video course in English

The speaker: Corey Shafer

Course Link: [Visual Studio Code (Windows)](https://www.youtube.com/watch?v=-nh9rCzPJ20&list=LLOujATZg4TQCBODShG4Fv9w)

### Installation - 1:13

nothing special

### Python Extension - 5:48

Go to icon *Extenstions* find *Python* and install

(Also *Code Runner*, see below)

### Switching Interpreters - 10:04

The example code:

    import math
    import sys

    # print the version and the location of my python
    print(sys.version)
    print(sys.executable)

    # define 
    def greet(who_to_greet):
        greeting = "Hello, {}".format(who_to_greet)
    return greeting

    print(greet("World"))
    print(greet("Corey"))`

Note:

1. Run the code: right mouse click, select *Run Python file in Terminal*
2. There will be a blue bar at the bottom of the VSCode Windows, Click it, we can change the interpreter.
3. To clean the terminal planet: cls
4. When the interpreter has been changed, a folder named *.vscode* is created inside the projekt.
5. In this folder there is a file called *setting.json*, which ist the new settings for the specific current workspace.

### Changing Color Themes, file icons - 12:35

1. Open command palette: Ctrl + Shift + P
2. Type Color Themes or File Icons
3. Select built-in or install new Options
4. Used Color Theme: install *Predawn Theme Kit*
5. Used File Icons: Ayu

### VSCode Settings - 16:16

For more settings: click the icon gear on the left bottom, then select *settings* (global user settings)

### Set Default Python - 21:33

Open *Settings*:

1. UI (user interface) switch to JSON format: click *Open Settings (JSON)* on the right top
2. The content in the file only shows what have been changed from the default
3. Open Default Settings: Command Platte: Default Settings (JSON). These are all the settins that the users can change.

The speaker uses the font *Source Code Pro* which can be downloaded from google font.

### Using Virtual Environments - 25:10

To create a virtual environment for a special project (practise to set up a special interpreter)

1. The easiest way is to use the venv module from the standard library: *python -m venv venv* (Created a new folder named venv)
2. Change the interpreter to venv: Click the blue bar at the bottom. Select the one with *'venv':venv*
3. Take care of the path, if the venv folder is outside the local project. Open .vssode/settings.json, change the path there
4. Terminal will be directly changed for venv

My pip doesn't work!

1. use pip to install: pip install requests

Add Code:

    import requests
    
    r = requests.get('http://coreyms.com')
    
    print(r.status_code)
    print(r.ok)

### IntelliSense - 29:45

IntelliSense is built in the VSCode.

1. select the word
2. right click
3. Go to Definition / Peek Definition

### Code Formatting - 32:13

1. use shortcut: go to Command Platte, type format.
2. Shift + alt + F: pop-up: Yes, Use Black, Use yapf
3. Select *Use black*
4. Use: Shift + Alt + F
5. Copy the settings to the file setting.json

editor.formatOnSave:true formats automatically anytime I save my file.
> Note: press *control + space*

To sort the code:

1. select content to be sorted
2. go to command palette(control + shift + P), type *sort imports*
 also e.g. *from os import rename*

### Code Linting - 37:06

Linter, pylint

linting: look at our code and tell us if it thinks that something is off  check the grammer before

### Code Runner Extension - 39:42

code runner: read the document. Don't forget to change the path or sth.

### Git Integration - 47:44

1. Click icon *Git*, click *+*
2. Don't want to upload all file:
    1. Create a file called .gitignore
    2. Type the file name
3. After change: click *+* beside each file, or select *stage all of the changes*
4. click 'check mark' to commit

Make some change
5. Go to github create a responsery
6. Copy linke -> connected with local and blabla

### Use Different Terminal - 51:07

[How to change the terminal](https://code.visualstudio.com/docs/editor/integrated-terminal)

### Debugging - 58:45

How to Debug:

1. add a breakpoint into the script
2. click *Debug*
3. *no configuration*: click *Gear*
4. green run: run code until the break point
5. see Debug: Locals
6. watch section: a specific variable: click "+"
7. loop
8. below windoes: select debug console: can be used like an interactive Python prompt
9. like type: r.ok, r.url
10. at the top there are 6 more options

### Unit Testing - 1:03:25

unit testing support (new code)

1. use cmd to open VSCode: code foldername. If not recognised: go to command palette, type *shell/code* (not solved)
2. open files
3. open CP: type *discover tests*, then pop-up *Enable and configure a Test Framework*, then click on that, then selection (unitest, pytest, nose), then select *unitest*, then select *test_*py*
4. different trys

### Zen Mode - 1:09:55

find speaker's settings in his github (MAC)

one important thing added in this setting is Zen Mode:

>Zen mode is just their distraction free mode that allows you forcus more on your code and your output and hides a lot of the other menus and things that you might find distracting.

1. open CP: type zen
2. open up Zen Mode

#### keyboard shortcuts: search

find in CP: type *keyboard shortcuts*, select *Help: Keyboards Shortcus Preference*

    control + ~ : open terminal
