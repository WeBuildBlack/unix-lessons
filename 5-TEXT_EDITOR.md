# Our first text editor  
This whole time we've been creating blank files. Not much we can do with that. In this lesson we'll be exploring the `vi` command, short for "visual editor", to add text to files.  

There are two "modes" in `vi`: input mode and edit mode. Input mode is for typing text into a file. Edit mode is for manipulating the file structure. For example, things like deleting, searching. copying, replacing, and saving would be done in edit mode. Let's create a file and edit it now.
```console
user@bash: ls
file1.txt
user@bash: vi file2.txt
```
`vi` will actually make the file if you try to run it on a file that doesn't exist. When you open up the file2.txt you should see something that looks like this:
```console
~
~
~
~
~
"file2.txt" [New File]
```
You're now in edit mode. If you want to enter into input mode hit the **i** key. Your screen should look like this:
```console
~
~
~
~
~
-- INSERT --
```
After typing in a few words you can hit the **ESC** key and go back into edit mode.

## Saving and Exiting
`vi` actually gives you a few ways to go about saving and exiting. Here are some options:
* __ZZ__ (in capitals) - Save and exit
* __:q!__ - discard all changes, since the last save, and exit
* __:w__ - save file but don't exit
* __:wq__ - again, save and exit

Also, any command that begins with __:__ needs you to press **Enter** to complete.

## View a file
If you want to just view a file use the `cat` command. It stands for concatenate and is usually used to join files together. Still, we can use it to view files by running it on one file:
```console
user@bash: cat file.txt
this is some text content
from a file that we used
the cat command on
user@bash: 
```

## Moving around a file in Vi
Here's a quick rundown of the main commands when moving around a file in Vi:
* Arrow keys - move the cursor around
* j, k, h, l - move the cursor down, up, left and right (similar to the arrow keys)
* ^ (caret) - move cursor to beginning of current line
* $ - move cursor to end of the current line
* nG - move to the nth line (eg 5G moves to 5th line)
* G - move to the last line
* w - move to the beginning of the next word
* nw - move forward n word (eg 2w moves two words forwards)
* b - move to the beginning of the previous word
* nb - move back n word
* { - move backward one paragraph
* } - move forward one paragraph 8

## Deleting content
Here are a few ways to delete from files when using `vi`:
* x - delete a single character
* nx - delete n characters (eg 5x deletes five characters)
* dd - delete the current line
* dn - d followed by a movement command. Delete to where the movement command would have taken you. (eg d5w means delete 5 words)

## Undoing
Here are the commands for undoing in `vi`:
* u - Undo the last action (you may keep pressing u to keep undoing)
* U (Note: capital) - Undo all changes to the current line

## Stick around for the next episode...
These past lessons we've been dealing with single files and directories. In the next lesson we'll be showing you how to select multiple.