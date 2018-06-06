# What is Unix?
Unix is an **operating** system built by the good people over at [Bell Labs](https://www.bell-labs.com/about/history-bell-labs/).

# What is an operating system
An operating system is the software that gives your computer it's basic functions such as scheduling tasks and opening applications. Two well known examples of operating systems are Windows and Mac OS.

### A command line, or terminal, is a text based interface to the system. You are able to enter commands by typing them on the keyboard and feedback will be given to you similarly as text.


```console
user@bash: ls -l /home/devin
total 3
drwxr-xr-x  2 ryan users 4096 Mar 23 13:34 bin
drwxr-xr-x 18 ryan users 4096 Feb 17 09:12 Documents
drwxr-xr-x  2 ryan users 4096 May 05 17:25 public_html
user@bash:
```

user@bash = prompt  
ls = command <===== usually goes first  
-l /home/ryan = command line arguments <===== goes after command  
lines 2-5 = output <===== not every command displays output  

Inside the terminal is a shell. A shell defines how a terminal looks and behaves when executing your commands.
The most common shell is Bash. Bash stands for Bourne again shell. The reason for this is that the Bash shell is a successor to an older shell called the Bourne shell that was mad by Stephen Bourne at
Bell Labs.

If you want to be sure what shell you're system is using enter this into your terminal:

```console
user@bash: echo $SHELL
```

A quick shortcut: If you press the up and down key in the terminal you can see the history of commands you've typed. This is great if you want to be lazy and not type an old command over again.