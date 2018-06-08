# Read the manual!
Nobody remembers everything. Especially not me. That being said, unless you're some all-knowing God, you probably need a manual to remember all the Unix terminal commands. `man` is a command that lets us see the manual page on another command. For example:  
```console
user@bash: man ls
Name
    ls - list directory contents
 
Synopsis
    ls [option] ... [file] ...
 
Description
    List information about the FILEs (the current directory by default). Sort entries alphabetically if none of -cftuvSUX nor --sort is specified.
 
    Mandatory arguments to long options are mandatory for short options too.
 
    -a, --all
        do not ignore entries starting with .
 
    -A, --almost-all
        do not list implied . and ..
 
...
```
As you can see above, we've ran the `man` command with `ls` as an option. It returns us the manual page for the `ls` command. This contains the command name, format for how to use the command (synopsis), a short description, and a listing of all the options associated to it.

## Searching
If you'd ever like to search for a keyword in the manual, you can use `man -k <keyword>`. Replace `<keyword>` with whatever your search term is. Press `n` for next to see the next occurence of the keyword. If you are looking at a command's manual page already, you can search by typing `/<keyword>` and then pressing Enter.

## Stick around for the next episode...
In the next lesson we'll dig a little deeper into files and how to interact with them. Click [here](https://github.com/WeBuildBlack/unix-lessons/blob/master/3-FILES.md) to go there now.

## Stick around for the next episode...
In the next lesson we'll be getting more serious with files. Do you feel us getting closer to the juicy stuff? Soon you'll be a Unix beast!