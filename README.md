# linux_learning
learning linux command line (BASH) 

## Soruce of materials
Ryan's Tutorials: https://ryanstutorials.net/linuxtutorial/
Ryan's email:ryantutorial@todolistme.net

# Introduction 
## Goal of learning: Not to become a Unix guru, just to enjoy more convenience in programming, to be able to appreciate the beauty of programming more, and ofcourse add one more skill under your belt

## Contents to cover
-command line Vs. Graphical User Interface(GUIs)
-directory system
-file manipulation
-regular expressions
-ping, reping, redirection
-wildcards
-scripting
-process management

## Tips to go
Explore and experiment
Read carefully
General approach: hypothesis--command to test the hypothesis---observe and analyze the output---iterate till problem solved

## SSH clients: 
Windows Power Shell, Putty, etc. 
Bash stands for Bourne again shell.
Use the command "echo $SHELL" to find out which shell you are currently using

# Command Line (terminal running Bash)
example line:ls -l /home/ryan
 Comman should be typed after the command prompt.
 If no prompt is displayed then the command may still be running.
 The above command line consists of a command ( ls ) and its command line arguments ( -l /home/ryan )
 There must be a space between the command and the first command line argument also). The first command line argument ( -l ) is also referred to as an option. Options are typically used to modify the behaviour of the command. Options are usually listed before other arguments and typically start with a dash ( - ).
 
 ## Tip:
 Use up and down arrows to review previously entered commands, and use left and right arrows to edit one
 
 # Directory system
 1. pwd  print the working directory
 As many commands rely on you being in the right location (directory), it's important to understand where you are to start with. 
 2. ls  list
 Now we need to know what's in there. First we can get a plain listing of things at our current directory. 
 Syntax of ls: ls [options][location]
 Next, let's try some arguments
 3. ls -l  to get a long listing, which includes the following:
-First character indicates whether it is a normal file ( - ) or directory ( d )
-Next 9 characters are permissions for the file or directory  .
-The next field is the number of blocks  .
-The next field is the owner of the file or directory  .
-The next field is the group the file or directory belongs to .
-Following this is the file size.
-Next up is the file modification time.
-Finally we have the actual name of the file or directory.
 5. ls /etc
 This argument /etc tells ls not to list our current directory, but instead to list that directories' contents. 
 6. ls -l /etc  (run ls with both its option and argument)
 7. cd [location] if run without argument, it will take you back to the home directory. If with argument,it will change directory for us. 
 8. 

## Path
Path is important in being proficient with Linux
Whenever we refer to either a file or directory on the command line, we are in fact referring to a path. ie. A path is a means to get to a particular file or directory on the system.
There are 2 types of paths we can use, absolute and relative.
The file system under linux is a hierarchical structure. At the very top of the structure is what's called the root directory. It is denoted by a single slash ( / ). It has subdirectories, they have subdirectories and so on. Files may reside in any of these directories. 

Absolute paths specify a location (file or directory) in relation to the root directory. You can identify them easily as they always begin with a forward slash ( / )
Relative paths specify a location (file or directory) in relation to where we currently are in the system. They will not begin with a slash.

## Tip
~ (tilde) - This is a shortcut for your home directory. eg, if your home directory is /home/ryan then you could refer to the directory Documents with the path /home/ryan/Documents or ~/Documents
. (dot) - This is a reference to your current directory. eg in the example above we referred to Documents on line 4 with a relative path. It could also be written as ./Documents (Normally this extra bit is not required but in later sections we will see where it comes in handy).
.. (dotdot)- This is a reference to the parent directory. You can use this several times in a path to keep going up the hierarchy. eg if you were in the path /home/ryan you could run the command ls ../../ and this would do a listing of the root directory.

Whenever you refer to a file or directory on the command line you are actually referring to a path and your path can be constructed using any of these elements. The best approach is whichever is the most convenient for you.

## Another Tip
Tap completion is very helpful when typing paths. 
When you start typing a path (anywhere on the command line, you're not just limited to certain commands) you may hit the Tab key on your keyboard at any time which will invoke an auto complete action. If nothing happens then that means there are several possibilities. If you hit Tab again it will show you those possibilities. You may then continue typing and hit Tab again and it will again try to auto complete for you.

## Exercises
Let's start by getting familiar with moving around. Use the commands cd and ls to explore what directories are on your system and what's in them. Make sure you use a variety of relative and absolute paths. Some interesting places to look at are:
/etc - Stores config files for the system.
/var/log - Stores log files for various system programs. (You may not have permission to look at everything in this directory. Don't let that stop you exploring though. A few error messages never hurt anyone.)
/bin - The location of several commonly used programs (some of which we will learn about in the rest of this tutorial.
/usr/bin - Another location for programs on the system.

