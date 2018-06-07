# What is Unix?
Unix is an **operating** system built by the good people over at [Bell Labs](https://www.bell-labs.com/about/history-bell-labs/).

# What is an operating system?
An operating system is the software that gives your computer its basic functions, such as scheduling tasks and opening applications. Two well known examples of operating systems are Windows and Mac OS.

### A command line, or terminal, is a text-based interface to the system. You are able to enter commands by typing them on the keyboard, and the result will be given to you as text.


```console
1 user@bash: ls -l /home/devin
2 total 3
3 drwxr-xr-x  2 ryan users 4096 Mar 23 13:34 bin
4 drwxr-xr-x 18 ryan users 4096 Feb 17 09:12 Documents
5 drwxr-xr-x  2 ryan users 4096 May 05 17:25 public_html
6 user@bash:
```
The first thing we see is `user@bash: `. This is called the the prompt. It usually display some variation of your username and the type of shell you have. On my Macbook it looks like this `Devins-Air:~ devinjackson$`. So don't feel bad if you're prompt looks different.  
Next we see `ls` which is the command we are trying to execute. After that is `-l`, which is an option to the command. These modify how the command actually does what it does. Options can also sometimes be referred to as flags.  
Next is `/home/devin` which is the command parameter. Parameters are the thing that you would be running the command on. Parameters are also referred to as values sometimes.  
Lines 2-5 is the result that the command outputs to us. Be aware that not every command returns an output.  

Inside the terminal is a shell. A shell defines how a terminal looks and behaves when executing your commands.
The most common shell is bash. It was created by Brian Fox. The bash shell is a successor to an older shell called the Bourne shell that was made by Stephen Bourne at Bell Labs. Bash stands for Bourne Again SHell.

If you want to be sure what shell your system is using, enter this into your terminal:

```console
user@bash: echo $SHELL
```

A quick shortcut: If you press the up and down key in the terminal, you can see the history of commands you've typed. This is great if you want to be lazy and not type an previous command.