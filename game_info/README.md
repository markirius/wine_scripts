## game_info directory

This directory is required for script to work properly. At least, never
remove game_info.txt file and data directory.

Other directories and fiels are not strictly necessary and can be optionally
removed or not created.

## Directories/files description:

* game_info.txt - information about the game
* data - directory containing game files
* dlls - libraries and other files intended to put into system32 directory
* additional - specific files (for example, settings for games or fonts)
* regs - tweaks for registry
* exe - executable files (mostly, installers of different programs)
* sh - scripts that will be executed during prefix creation
* icon - game icon file, tools.sh use it for desktop file

## WINETRICKS:

* winetricks_list.txt - list of components to install using winetricks

During prefix creation winetricks will automatically install all components
and apply all tweaks from winetricks_list.txt file. Write names of components
and tweaks in first line, separated by a space.

For example: d3dx9 corefonts xact dxvk win8.

## Directories description:

### data directory

Put game files here.

## dlls directory

Put here ibraries and other files intended to put into system32 directory

Script will automatically copy them to windows/system32 directory. And also
it will automatically override them to "Native" and will register them
using regsvr32.

You cat put here not only dlls but also files with any other extensions.

## exe directory

Put executable files here (for example, installers).

Script will automatically execute all files from this directory during
prefix creation.

## regs directory


Put registry files here.

Script will automatically import all reg files from this directory during
prefix creation.

## sh directory

Put custom shell scripts here.

Script will automatically execute all scripts from this directory
during prefix creation.

## sh/everytime directory

Put custom shell scripts here.

Script will automatically execute all scripts from this directory
each time the game/application launches.

## additional directory

Put any custom files/directories there. The names of directories should
be the same as the name of directories you want to copy to. For example:


The content of game_info/additional/prefix/drive_c/Windows/Fonts directory
will be copied to prefix/drive_c/Windows/Fonts directory during prefix
creation.

The content of game_info/additional/documents/Domcuments_Multilocale/My Games/Fallout4
directory will be copied to documents/Domcuments_Multilocale/My Games/Fallout4
directory during prefix creation.

Etc.
