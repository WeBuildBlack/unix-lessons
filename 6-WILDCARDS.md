# Wildcards
We always want to be as efficient as possible when working as a programmer. In the past I've shown how to run commands on singular files & directories. Let's look at how we can use wildcards to refer to multiple files/directories and make our lives easier.

## What's a wildcard bruh?
Wildcards are symbols that allows to make paths that refer to multiple files and directories. Instead of a path that goes to only one file, you create a pattern. That pattern will refer to any file/folder that it applies to.   
These are the fundamental wildcards:
* `*` - represents zero or more characters
* `?` - represents a single character
* `[]` - represents a range of characters

## The star of the show
Let's start with the `*` and see it in action below.
```console
user@bash: pwd
/home/devin/tutorials
user@bash: ls
barry.txt blah.txt bob example.png firstfile foo1 foo2
foo3 frog.png secondfile thirdfile video.mpeg
user@bash: ls b*
barry.txt blah.txt bob
user@bash: 
```
Essentially what `ls b*` is doing is telling the terminal to find everything in the current directory, that starts with "b", and can have either nothing or anything after it.  
That's pretty general though. What if I wanted to find all the files in my Documents folder ending in ".txt". I'd do something like this:
```console
user@bash: ls /home/devin/Documents/*.txt
example1.txt example2.txt
```

## Question mark
The question mark stands in place of any single character. So if I wanted to find any file that had __i__ as it's second letter in my Music folder I would do this:
```console
user@bash: ls /home/devin/Music/?i*
big-song.mp3 video.mp4
```

## The range
The brackets are a way for you to specify a range of characters. For example, if I wanted to find an image file in my current directory that started with a lowercase letter, then a single digit, and then ended with ".jpg" I would do this:
```console
user@bash: ls [a-z][0-9]*.jpg
C4-explosion.jpg
```

## Stick around for the next episode...
That was pretty cool right? Now we don't have to just run `ls` on a whole directory and see everything. Sometimes we just wanna see a few files. In the next lesson we'll talk about permissions.