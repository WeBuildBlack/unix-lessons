# Files on files  
In this lesson we're gonna do a deep dive into files so that in the future when we start working with them more you're more informed as to what is going on.

## Everything is a file
In Unix, under the hood, everything is a file. I know that sounds crazy but it's true. Text files are files, directories are files. Your keyboard is a file too. When you hit a key, the computer will read from the keyboard file to see what letter is associated to that key, and then print it out. Your monitor is a file too. When something on the screen changes, your computer writes to the monitor file to change the pixel colors on screen. This really has no bearing on the work we'll be doing, but it's good to know how things work.

## File Extensions
A file extension is the 2-4 characters that come after the last dot in a file. The purpose is to let you know what kind of file it is. For example:
* file.exe - an executable program
* file.txt - a text file
* file.jpg - a image file

On systems like Windows, the computer will read the file extension and take that as the truth. So if I have an image file, file.jpg, and change the file name to file.txt, then Windows will more than likely see the file as corrupted. Unix is a bit different and actually reads the file contents to figure out the file type rather than solely relying on the file extension. So if I was to do the same thing on a Unix system it would still read the file as an image.

This creates confusion when looking at a file in Unix because you don't know if someone maliciously changed the extension to look like a different type of file. Luckily we have a `file` command for that.

```console
user@bash: file /home/devin/Documents/data.txt
data.txt: ASCII text
```

### Remember: Linux is Case-sensitive!
I know some of you coming from Windows are used to terminals being case-insensitive but Unix is NOT like that. When referring to files and directories, remember to use the exact casing or it will not be found. Options on commands are also case sensitive. For example the `-s` option on the `ls` command is a totally different option than `-S`. So be aware of your casing!

## Spaces in file names
Sometimes we have file names that have a space in them. How we refer to them is different though. For example if we wanted to go to the "Shooter Games" directory this wouldn't work:  
```console
user@bash: ls
Shooter Games ActionGames
user@bash: cd Shooter Games
bash: cd: Shooter: No such file or directory
```
This fails because the terminal will read Shooter and Games as two different commands. There are two ways to get around this issue.

### Quotes
You can use quotes (single or double) to specify the path to the file/directory you want. For example:
```console
user@bash: ls
Shooter Games ActionGames
user@bash: cd 'Shooter Games'
user@bash: pwd
/home/devin/Shooter Games
```
### Escape Characters
The other method is the escape character, AKA the backslash (`\`). The escape character will nullify any special meaning to the character after it. For example:
```console
user@bash: ls
Shooter Games ActionGames
user@bash: cd Shooter\ Games
user@bash: pwd
/home/devin/Shooter Games
```

## Hidden files and directories
Files and folders can be hidden by adding a dot(.) at the beginning of the file name. When using the `ls` command, you will not see any hidden files. If you use the `-a` option, short for all, then it will show all files including hidden ones. For example:
```console
user@bash: ls
FILE1.txt File1.txt file1.TXT
user@bash: ls -a
FILE1.txt File1.txt file1.TXT .hidden .file.txt
```

## Stick around for the next episode...
In the next lesson we'll go into how to use the manual command. Don't worry, I won't bore you I promise. It'll be quick ;)