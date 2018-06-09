# Do you have permission to do that???
Permissions in Unix are exactly what they sound like. They give certain people permission to do things to files. Let's be honest, if you shared your computer with your little brother, would you want him to be able to delete your pictures?

## What are som permissions?
The 3 things that permissions allow you to do is read, write, and execute. Unix gives each of these permissions a letter:
* `r` read - you can see the contents of a file
* `w` write - you can write content to a file
* `x` execute - you can run a file

There are also 3 different types of groups for permissions:
* **owner** - the user who owns the file
* **group** - all files belong to one group
* **others** - all other users that are not the owner or in the group

## View Permissions
If you remember before we could use the `-l` option for the `ls` command to see the permissions of a file. Let's do that now to understand it better:
```console
user@bash: ls -l /home/devin/tutorials/house.png
-rwxr----x 1 joseph users 2.7K Feb 12 09:16 /home/devin/tutorials/house.png
```
That first part where you see `-rwxr----x`, is the permissions. Let's break this down:
* The first character identifies the file type. If it is a dash "-" then it is a normal file. If it is a "d" then it is a directory.
* The following 3 characters represent the permissions for the **owner**. A letter represents the presence of a permission and a dash ( - ) represents the absence of a permission. In this example the owner has all permissions (read, write and execute).
* The following 3 characters represent the permissions for the **group**. In this example the group has the ability to read but not write or execute. Note that the order of permissions is always read, then write then execute.
* Finally, the last 3 characters represent the permissions for **others** (or everyone else). In this example they have the execute permission and nothing else.

## Changing Permissions
Changing permissions requires us to the use the `chmod` command, short for "change mode". This is the formula for a `chmod` commmand:  
`chmod <permissions> <path>`  
If we're going to be using this command, there are three things that we need to specify:
* Who are we changing the permissions for? "u" (user AKA owner), "g" (group), "o" (others), or "a" (all)
* Are we giving or taking away permissions? "+" for giving an "-" for taking away
* Which permissions are we setting? "r" (read), "w" (write), or "x" (execute)

Here are some examples to help you understand:  
```console
1 user@bash: ls -l trees.png
2 -rwxr----x 1 joseph users 2.7K Jan 4 07:32 trees.png
3 user@bash: chmod g+x trees.png
4 user@bash: ls -l trees.png
5 -rwxr-x--x 1 joseph users 2.7K Jan 4 07:32 frog.png
6 user@bash: chmod u-w trees.png
7 user@bash: ls -l trees.png
8 -r-xr-x--x 1 joseph users 2.7K Jan 4 07:32 trees.png
```
It's also possible to set multiple permissions at once.
```console
1 user@bash: ls- l trees.png
2 -rwxr----x 1 joseph users 2.7K Jan 4 07:32 trees.png
3 user@bash: chmod g+wx frog.png
4 user@bash: ls -l trees.png
5 -rwxrwx--x 1 joseph users 2.7K Jan 4 07:32 trees.png
6 user@bash: chmod go-x trees.png
7 user@bash: ls -l trees.png
8 -rwxrw---- 1 joseph users 2.7K Jan 4 07:32 trees.png
```
You may be confused as to why an owner would remove their rights to read, write, or execute on a file. There are a few reasons for this. One might be that you have a file with sensitive data and you don't want to accidentally overwrite/delete it.  

These same permissions apply to directories, except the actions attached to permissions is a bit different. The "read" permission allow you to see content inside, an `ls` command for example. "Write" permissions allow you to create files inside the directory. "Execute" permissions allow you to enter into a directory, using `cd` for example.  

Also, if you would like to see the permissions on a specific directory you would use `ls -ld <path>` instead of `ls -l <path>`. The extra "d" stands for directory.

## Who's in charge?
There are only two kinds of users who can change somethings permissions. The **root** user and the file/folder **owner**. **Root** users are allowed to do whatever they want on the system and are part of the **superuser** group. Typically, you would have an administrator using this account to maintain the system. Every other user would login with their personal account, have access to only their files, and some files that are shared between accounts.  

## Stick around for the next episode...
In the next lesson, we'll be talking about how we can use filters to query files for specific data.