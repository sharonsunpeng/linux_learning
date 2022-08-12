# linux_learning (7 days)
learning linux command line (BASH) 

## Soruce of materials
1.Ryan's Tutorials: https://ryanstutorials.net/linuxtutorial/
Ryan's email:ryantutorial@todolistme.net
2. Shell Scriting Tutorial for Beginners, youtube playlist provided by the channel ProgrammingKnowledge
https://youtube.com/playlist?list=PLS1QulWo1RIYmaxcEqw5JhK3b-6rgdWO_ 
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
 8. file [path]  to find out what type of file a particular file is

## Path
Path is important in being proficient with Linux
Whenever we refer to either a file or directory on the command line, we are in fact referring to a path. ie. A path is a means to get to a particular file or directory on the system.
There are 2 types of paths we can use, absolute and relative.
The file system under linux is a hierarchical structure. At the very top of the structure is what's called the root directory. It is denoted by a single slash ( / ). It has subdirectories, they have subdirectories and so on. Files may reside in any of these directories. 

Absolute paths specify a location (file or directory) in relation to the root directory. You can identify them easily as they always begin with a forward slash ( / )
Relative paths specify a location (file or directory) in relation to where we currently are in the system. They will not begin with a slash.

whenever we specify a file or directory on the command line it is actually a path. Also because directories (as mentioned above) are actually just a special type of file, it would be more accurate to say that a path is a means to get to a particular location in the system and that location is a file.

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
Try running the command file giving it a few different entries. Make sure you use a variety of absolute and relative paths when doing this.
Now issue a command that will list the contents of your home directory including hidden files and directories.


## Cool facts to me
Ok, the first thing we need to appreciate with linux is that under the hood, everything is actually a file. A text file is a file, a directory is a file, your keyboard is a file (one that the system reads from only), your monitor is a file (one that the system writes to only) etc. 

A file extension is normally a set of 2 - 4 characters after a full stop at the end of a file, which denotes what type of file it is. The following are common extensions:
file.exe - an executable file, or program.
file.txt - a plain text file.
file.png, file.gif, file.jpg - an image.
Under Linux the system actually ignores the extension and looks inside the file to determine what type of file it is.
There is a command called file which we can use to find this out the type of file a particular file is. 
fiel[path]

whenever we specify a file or directory on the command line it is actually a path. Also because directories (as mentioned above) are actually just a special type of file, it would be more accurate to say that a path is a means to get to a particular location in the system and that location is a file.


## Escape characters
 a backslash ( \ ). What the backslash does is escape (or nullify) the special meaning of the next character.
 In the previous section we learnt about something called Tab Completion. If you use that before encountering the space in the directory name then the terminal will automatically escape any spaces in the name for you.
 
 ## Hidden files and directories
If the file or directory's name begins with a . (full stop) then it is considered to be hidden
To make a file or directory hidden all you need to do is create the file or directory with it's name beginning with a . or rename it to be as such. Likewise you may rename a hidden file to remove the . and it will become unhidden. The command ls which we have seen in the previous section will not list hidden files and directories by default. We may modify it by including the command line option -a so that it does show hidden files and directories. "ls -a PATH"


file
obtain information about what type of file a file or directory is.
ls -a
List the contents of a directory, including hidden files.
Everything is a file under Linux
Even directories.
Linux is an extensionless system
Files can have any extension they like or none at all.
Linux is case sensitive
Beware of silly typos.


## Manual pages
man <command to look up>
eg. man ls
The manual pages are a set of pages that explain every command available on your system including what they do, the specifics of how you run them and what command line arguments they accept.The man pages are your friend. Instead of trying to remember everything, instead remember you can easily look stuff up in the man pages.
To exit the man pages press 'q' for quit.


man <command>
Look up the manual page for a particular command.
man -k <search term>
Do a keyword search for all manual pages containing the given search term.
/<term>
Within a manual page, perform a search for 'term'
n
After performing a search within a manual page, select the next found item


** ## Long hand Vs short hand**
 
 long hand command line options begin with two dashes ( -- ) and short hand options begin with a single dash ( - ).
 The long hand is really just a more human readable form. You may use either, they both do the same thing. One advantage of using long hand is that it can be easier for you to remember what your commands are doing. One advantage of using shorthand is that you can chain multiple together easier. When we use a single dash we may invoke several options by placing all the letters representing those options together after the dash. 
 
 
