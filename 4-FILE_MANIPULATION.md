# The fun stuff: Manipulating files!
Ok, so now that we've had you do the Mr. Miyagi and go through the foundations, we can start doing all the cool stuff. Let's talk about creation.

## Making Directories
We've done all this work climbing through folders, but how do we actually make one? Ladies and gentlemen, I give you the `mkdir` command! Short for Make Directory. For example:
```console
user@bash: pwd
/home/devin
user@bash: ls
Documents Downloads
user@bash: mkdir tutorial_files
Documents Downloads tutorial_files
```
### Some options for ya
`mkdir` also provides a bunch of options, two of which I find really useful. The `-p` option, for parent, creates parent directories as needed. For example:
```console
user@bash: pwd
/home/devin
user@bash: ls
Documents Downloads
user@bash: mkdir -p tutorials/foo/bar
user@bash: ls
Documents Downloads tutorials
user@bash: cd tutorials/foo/bar
user@bash: pwd
/home/devin/tutorials/foo/bar
```
Using the `-p` option, we created a parent directory called "tutorials", the child "foo" directory under that, and then the child "bar" directory under that. This is much easier than doing the `mkdir` command one by one.

## Creating files: The Magic Touch
We'll find ourselves in a lot of situations where we need to create a file. `touch` is a command that creates a blank file using whatever name and extension you give it. For example:
```console
user@bash: pwd
/home/devin/tutorials
user@bash: ls
foo
user@bash: touch example1.txt
user@bash: ls
foo example1.txt
```
## Such a copycat
I'm not the biggest fan of doing things twice. I'm lazy, what do you want from me. That being said, I love the `cp` command. It's short for "copy". Watch this:
```console
user@bash: ls
example1.txt foo
user@bash: cp example1.txt new.txt
user@bash: ls
example1.txt new.txt foo
```
Let's break this down. I used `cp` to copy `example.txt` to the another file called `new.txt` in the same directory. If I wanted to put it in another directory I could use an absolute or relative path. For example:  
```console
user@bash: cp example1.txt /home/devin/Documents/new.txt
```
That's how we copy files but how do we copy directories? We use the `-r` option for that. The `-r` is short for recursive. Recursive means look at a directory and all files and directories within it. Then for child directories, go into them and do the same thing over and over til you hit the end. For example:
```console
user@bash: ls
Documents Downloads tutorials
user@bash: ls tutorials
foo bar more
user@bash: cp -r tutorials ./more-tutorials
user@bash: ls
Documents Downloads tutorials more-tutorials
user@bash: ls more-tutorials
foo bar more
```
# Moving Files & Directories
To move a file or directory we use the `mv` command. For example:  
```console
1 user@bash: pwd
2 /home/devin/tutorials
3 user@bash: ls
4 foo bar example1.txt example2.txt
5 user@bash: mv example.txt foo/example1.txt
6 user@bash: ls
7 foo bar example2.txt
8 user@bash: ls foo
9 example1.txt
10 user@bash: mv example2.txt bar/moved-file.txt
11 user@bash: ls bar
12 moved-file.txt
```
Line 1 - We check where we're at by printing out the current working directory  
Line 3 - We check what's in the folder  
Line 5 - We moved the example1.txt file inside the foo folder
Line 10 - We moved the example2.txt file inside the bar folder and renamed it moved-file.txt  

`mv` also doubles as a command to rename files and directories. If you want to rename something but not move it to a different directory, just rename it in the same directory. For example:  
```console
user@bash: ls
foo.txt bar.txt
user@bash: mv foo.txt new.txt
user@bash: ls
bar.txt new.txt
```

## Destroy! Destroy! Destroy!
Ok, maybe this header is a bit too much. I will be showing you how to remove directories and files using the `rm` command though. Check this out:
```console
user@bash: ls
foo.txt bar.txt more-files
user@bash: rm foo.txt
user@bash: ls
bar.txt more-files
```
BAM! We destroyed... uhhh I mean we removed the bar.txt file. Now, how do we remove directories? The `-r` option, for recursion again, does the same thing as `cp` but instead removes all the files/folders within.
```console
user@bash: ls
bar.txt more-files
user@bash: rm -r more-files
user@bash: ls
bar.txt
```

## Stick around for the next episode...
In the next lesson we're gonna start using the editor and putting some content in these files. You're getting good at this. Soon you'll be hacking into people's WiFi. Seriously don't do that though.