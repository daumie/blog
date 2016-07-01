---
layout: post
title: Parts Of A Command
date:   2016-06-28 15:50:39  
categories: terminal
---

Here are the parts of a Unix command:

	commandname [argument]… [<inputfile] [> outputfile]

## Commandname

The first word you type on a line is the commandname you wish to run.Some commands consist of only command name such as CLS which clears the computer screen 

	$ cls

`date` is the commandname in the example below.

	$ date --utc

---

## arguments

If there are any arguments to the command, they follow the command name.In the above example `--utc` is the argument.

---

## inputfile

If there is an input redirection symbol “<”, input comes from _inputfile_, otherwise it comes from the keyboard.For example, to get the command input for the sort command from File.txt: 

	$ sort < file.txt 

---
 
## outputfile

If there is an output redirection symbol “>”, output is sent to _outputfile_, otherwise it is sent to the screen.

	$ ls > file.txt


---

It is also possible to link up several commands so that the output of each command is used as the input of the next command:

	command1 | command2 | … | commandn