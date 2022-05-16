

From Ryans Tutorials Linux [Tutorial](https://ryanstutorials.net/linuxtutorial/)

## The Command Line

The command line refers to a text-based environment that allows the user to interact with their workstation. The command line terminal typically launches a default shell e.g. `/bin/bash`. The shell is a REPL that allows the user the enter commands, process them in some way, then see results and continue to enter more commands. Bash can also be run non-interactively via scripting.
  
## Basic Navigation

Without a visual analogy of files and folders found in the GUI, navigating the command line requires knowing how your system files are structured and which commands to use for traversal. Linux systems use a `/`to denote the root of the current file system. 

- `ls` is a common command to display a list of files. The command accepts arguments to change the default behavior of displaying the files in the current working directory in a simple list.
  - Adding the argument `-l` will give a long list with more details on each file.
- An absolute path will always begin at the root of the file system e.g. `/home/ben`. 
- A relative path begins from the current working directory.
- `cd` changes the current working directory.
- `pwd`prints the current working directory.

## More About Files

Everything on a Linux system is a file. Adding extensions to files are only used to make the contents of the file easier to understand but there is nothing stopping you from storing a jpeg encoded image in a file ending in `.txt`. 

- Linux is case sensitive.
- Spaces tell Bash this is the end of a command or an argument. There are ways around this but it's better to just avoid. Using quotes around the file time or using a `/` to "escape" the space character will get around this issue if needed.
- By default the `ls` command will not display files that begin with a `.`. This can be use the "hide" files or folders.

## Manual Pages

The `man` command can be passed an argument of a topic and will open up a manual page on the topic if it exists. The manuals are displayed in the pager program `less` and there are commands inside of less used to traverse the pages, hitting `h` while in the less program will show all the commands from movement to searching.

- Man pages will give a description of the command, a synopsis on how to use it, and details about the optional or required arguments.

Commands in Linux often have more than one way to type an argument. A short way that is a `-` plus a single letter or a longer readable way that is prefixed with `--`. Sometimes commands will even take a BSD style argument that doesn't get prefixed with a dash.

## File Manipulation

Basic tasks on the command line involve making and deleting folders `mkdir` and `rmdir`, moving files `mv`, copying files `cp` and deleting files `rm`. `touch` can also be used to create an empty file or update the recorded time a file was updated/modified. 

Commands don't have an undo and deleting files skips the concept of the recycle bin. Destructive commands should be preformed carefully and paths should be double checked before performing them. Most destructive commands have an argument to make the command interactive and prompt when something will be deleted. `cp` and `mv` don't seem like they could be destructive but without `-i` or `--interactive` to make them interactive it can be very easy to overwrite an existing file of the same name.

## Cheat Sheet

[Ryans Tutorials Linux Cheat Sheet](https://ryanstutorials.net/linuxtutorial/cheatsheet.php)

