# Navigation
So let's talk a little about how we can move around our file system. This is important as many commands require you to reference the file system location when executing them.

## Where in the heck am I?
There are times we find ourself in a situation where we need to know where exactly we are in the file system. For that we use a command called `pwd`, which stands for Print Working Directory. A lot of commands are abbreviations for the action they actually do. This makes it easier on us to remember and do our jobs. So now if we type  `pwd` in our terminals and press Enter the terminal will print out the path to the directory we're in.

```console
user@bash: pwd
/home/devin
user@bash: 
```

Also if you're wondering what a directory is it's just another name for a folder on a computer.

## What's in here?
So now that we can see what folder we're in we want to know what's actually in the folder. We have the `ls` command for that. `ls` is short for list, as in list out everything in this folder. Let's give it a try.

```console
user@bash: ls
bin Documents public_html
user@bash: 
```
You can see it lists out the contents of the current folder you're in. What if we wanted to see the contents of another directory? `ls` can also be executed using another location.

```console
user@bash: ls Documents
index.html essay.docx Pictures
user@bash: 
```
As you can see when we told `ls` to use the Documents folder as the location it actually prints out the contents of Documents instead of the current directory we're in.

## So much variety!
Remember we discussed before how commands also have arguments sometimes. Let's use one of those and see what it looks like. `ls` has an argument `-l` which stands for long. What this will do is instead of just printing out the contents of the folder it will give a longer description than just a name. Let's see that in action.

```console
user@bash: ls
bin Documents Downloads
user@bash:
user@bash: ls -l
total 3
drwxr-xr-x  2 devin users 4096 Mar 23 13:34 bin  
drwxr-xr-x 18 devin users 4096 Feb 17 09:12 Documents  
drwxr-xr-x  2 devin users 4096 May 05 17:25 public_html  
user@bash:
user@bash:ls /etc  
a2ps.cfg aliases alsa.d cups fonts my.conf systemd  
user@bash: ls /etc  
a2ps.cfg aliases alsa.d cups fonts my.conf systemd  
...  
user@bash: ls -l /etc  
total 3  
-rwxr-xr-x  2 root root 123 Mar 23 13:34 a2ps.cfg  
-rwxr-xr-x 18 root root 78 Feb 17 09:12 aliases  
drwxr-xr-x  2 ryan users 4096 May 05 17:25 alsa.d  
...  
user@bash: 
```