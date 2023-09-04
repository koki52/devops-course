# Shell

Similar to GUI, shell is an interface, used to interact with the computer. It is purely textual, a lot more simplistic than the GUI. In that way, it offers more lightweight interaction (GUI having a lot of overhead) and using less bandwidth. Both of those reasons are why it is preferred when interacting with remote servers. Learning the basics is important as it is the most common way of interacting with linux servers.

## Filesystem navigation

The first thing to cover will be the basics of filesystem navigation - where we are located, what we have there and how to move elsewhere.

```
# where we are - prints the current directory
$ pwd

# what is present in the directory - list contents
$ ls

# list additional details
$ ls -alh

# how to move around - change directory
$ cd Desktop

# move back to the default directory - home
$ cd

# move to the parent directory
$ cd ..
```

This allows us to move through the directories, but we need some extra commands to interact with files.

```
# create an empty file
touch file.txt

$ inspect the type of a file
file file.txt

$ show contents of the file
cat file.txt

$ use pager to navigate a longer file
less file.txt

$ edit a file
vim file.txt

$ delete a file
rm file.txt
```

## Using vim - basics

Vim is a bit different than an average text editor, having multiple modes and various shortcuts for faster text editing, although it may be difficult to learn at first. After opening an empty file, try entering the insert mode by pressing i on the keyboard. This mode is very similar to a conventional text editor, allowing navigation, inserting and deleting text. Write a few lines of text and press escape to return to the default mode.

Now pick a line and type dd to delete it. Type p to bring it back by pasting it. This combination can be used as a cut-and-paste mechanism. Copy-and-paste can be achieved by using the yy (yank) command instead of dd (delete). A single character can be deleted by typing x.

Commands can be applied to multiple rows by using a number in front, for example typing 5dd will delete 5 lines.

Vim can be exited from the default mode in one of several ways:
- :q exits if no changes were made
- :wq exits saving the changes
- :q! exits discarding the changes
