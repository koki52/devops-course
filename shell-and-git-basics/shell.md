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

## Using commands in the shell

We have already used some commands before, let's look at them in more detail. When using commands, the line consists of the command name, flags and arguments. For example, `ls -l /home/ubuntu` has them in that exact order. The name of the command shows which command we are using, the flags set some options to tweak how the command will be executed and the argument is the input for the command itself. In this case, we are using the ls (list) command, -l means we want the long output and /home/ubuntu is the path to the directory which the list command will use. We can use multiple flags and/or multiple arguments, but using none can also work when there are defaults.

How to know which flags and arguments are supported by the commands? Sometimes the -h or --help flags can help. More information is usually provided by the man (manual) command, providing a detailed manual for using the command. Try starting with `man man`. Relying on this can be more effective than googling, especially considering the implementations of certain commands can be different depending on the system.

## Redirecting input and output

Some commands may take text as input or you may want to redirect the output to a file. This can be done with < and > operators.

```
# use file as input for the command
$ cat < file.txt

# save output to a file (overwrite contents)
$ ls > file.txt

# append output to a file - try running it multiple times
$ ls >> file.txt

# heredoc - provide a multiline file in-place
$ cat << EOF
> bla
> bla bla
> EOF

# provide string as input
$ cat <<< "bla"
```

## Text filtering and manipulation

Some files may be too long to look through completely - sometimes we need to filter out just what we need. Less can help, we can use /bla (and press enter) to search for occurrences of bla in the file. Typing n will take us to the next occurrence and typing N will take us to the previous one. Another tool we can use is grep - providing it with the string we are looking for and giving text as input, it will output only the lines containing that text
