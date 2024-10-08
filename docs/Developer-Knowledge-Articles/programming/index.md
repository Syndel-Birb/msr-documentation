# Programming
We separated out the programming into two parts; the scripts which handle gameplay stuff like NPCs, weapons, and effects, and then the actual game code which handles the scripts and the actual mechanics.

## Programming
This is the mechanics of the game it self, to work with the game code you ARE expected to have an understanding of C++ and the Goldsrc engine.\ 
There's quite a few things we could always use help on that part.

To get started you can ask on our Discord about helping us program or if you prefer you can just start tackling issues [here](https://github.com/MSRevive/MasterSwordRebirth/labels/good%20first%20issue). There's a lot of other issues as well, but you will have to talk to someone on the development team about tackling those and work together with us. The best way to contact us as said earlier is through our Discord server.

### Compiling
We use CMake and Visual Studio 2022 and C++14 standard for compiling primarily, but we also want to have linux compatability one of these days so a GNU compiler would also work if you're interested in that. You can follow the [README](https://github.com/MSRevive/MasterSwordRebirth/blob/dev/README.md) page on the Repository on how to get started compiling.\
However, we do require some DLLs that are shipped with the game so you will need to contact us first on our Discord to get a Steam Key.

## Scripting
Majority of the game logic like NPCs and items are handled by the scripts, if you would like to contribute with that then feel free to look through the [MSCScripts Repository](https://github.com/MSRevive/MSCScripts) or feel free to ask in our Discord on what part you can help with!

Keep in mind currently the scripts are written in a proprietary languge that is very tempermental have basically 0 documentation, so you're better off asking how you can help with the scripts in our Discord.

In the future we plan on embedding [AngelScript](https://www.angelcode.com/angelscript/) and replacing the custom script language, and we plan on documenting the API as well.
