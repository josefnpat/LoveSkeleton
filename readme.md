LoveSkeleton

*A love2d skeleton generator*

**Requirements**

A linux system with lua installed.

**Usage**

    Usage: ./loveskeleton.lua [<libname>|love]

This lua script will fill in all the games and rebuild your main for easy orginization.

For example, you have a game and you want to have a map and a player.

    seppi@seppi7:~/Desktop/git/loveskeleton$ ./loveskeleton.lua map
    seppi@seppi7:~/Desktop/git/loveskeleton$ ./loveskeleton.lua player
    seppi@seppi7:~/Desktop/git/loveskeleton$ tree
    .
    |-- loveskeleton.lua
    |-- main.lua
    |-- maplib
    |   `-- maplib.lua
    |-- playerlib
    |   `-- playerlib.lua
    `-- readme.md
    
    2 directories, 5 files

This generated `maplib/maplib.lua` which has all of the love2d hooks in it, and they are already properly connected to the `main.lua`.

The philisophy of this script is that you should *never edit `main.lua`*. Every time you run the `loveskeleton.lua`, it overwrites `main.lua` so that all of the libraries proper hooks are in there. It is further encouraged to not use global variables, so each lib has it's own object defined. (map would have `maplib = {}`)

It is importiant to also note, that LoveSkeleton creates a global `state` variable that starts as `nil`.

If `love` is passes as the argument, the script will only rebuild the main.lua