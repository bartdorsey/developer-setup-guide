# Shell basics

## Using the keyboard

You never use the mouse to navigate in the shell, you always use the keyboard.
You can select text in the Terminal and copy it to the clipboard, but you can't
perform any actions with your mouse.  A common mistake is trying to move the location
of your typing cursor with the mouse.  

### Arrow keys

The left and right arrow keys are used for moving the cursor around within a line that you
are typing.

The up and down arrow keys scroll backwards and forwards through the history of
all the commands you've typed into your shell recently. You can also use the `history`
command to print out a list of all the commands you've used recently.

### Moving around in a line of text

You can move around a line of text by using the following handy keyboard shortcuts

- <kbd>Ctrl</kbd>+<kbd>A</kbd> or <kbd>Home</kbd> - Moves the cursor to the beginning of the line
- <kbd>Ctrl</kbd>+<kbd>E</kbd> or <kbd>End</kbd> - Moves the cursor to the end of the line
- <kbd>Alt</kbd>+<kbd>F</kbd> - Go right one word
- <kbd>Alt</kbd>+<kbd>B</kbd> - Go left one word

These are the most common ones, here's a more exhaustive list of [shell keyboard shortcuts]

### Kill foreground process

<kbd>Ctrl</kbd>+<kbd>C</kbd> in graphical operating systems often means to copy text to the clipboard.
This is not true in Unix or Linux.  <kbd>Ctrl</kbd>+<kbd>C</kbd> kills the **Foreground Process** running
in the terminal.  So if you have started up a program in the terminal and you would
like to stop it from running, <kbd>Ctrl</kbd>+<kbd>C</kbd> is your friend.  The shell is the one notable
exception to this, <kbd>Ctrl</kbd>+<kbd>C</kbd> does not kill the shell itself.

### Suspending the foreground process

One other thing you can do in the shell is to suspend a foreground
process so it pauses.  If you do this you get your shell prompt
back but the program is still technically in memory but paused or suspended.

<kbd>Ctrl</kbd>+<kbd>Z</kbd> suspends the current foreground program, and gives you your shell prompt back. To bring the program back to running in the foreground you can type the `fg` command.

You can make the program run in the background with the `bg` command.

> Be aware if you run a program in the background it will still output to your screen, and your prompt will ALSO be visible, so this can get pretty confusing. Usually it's better to just open a new terminal window

if you end up with multiple suspeded programs, you can list them with the `jobs` command.

Then you can add `%` followed by the number from the jobs list to either `fg` or `bg` to bring those programs to the foreground or the background.

### Exiting the Shell

A good thign to know how to do is how to exit a shell.  <kbd>Ctrl</kbd>+<kbd>D</kbd> or typing the command `exit` will cause the shell to quit. Sometimes (but not always depending
on the preferences) this will also close your Terminal.

### Tab completion

The <kbd>Tab</kbd> key can be used to trigger autocompletion of files, folders and sometimes
other things like command line flags etc.  The most often use is when typing in
a file path, you can hit <kbd>Tab</kbd> once after typing in a few letters and the shell
will attempt to autocomplete the rest of the file name. Hitting <kbd>Tab</kbd> again will
print out all of the matches. You can type a few more letters and hit <kbd>Tab</kbd> again
to trigger autocompletion again.

### Clearing and Resetting the Terminal

You can clear the terminal window by typing `clear` or by using <kbd>Ctrl</kbd>+<kbd>L</kbd>.

A more forceful `clear` is the `reset` command. Use reset anytime
a program has confused the terminal to the point where it is not
printing characters out correctly.

[shell keyboard shortcuts](https://defkey.com/bash-linux-unix-shell-shortcuts)

## Useful Commands

Here's a list of super useful commands you should learn.

- `pwd` Prints out the current working directory.
- `cd` Change Directory, when followed by a path, it changes the current working directory to that directory.
  - `cd` followed by nothing sends you to your home directory
  - `cd` followed by a `-` returns you to the previous directory
  - `cd` followed by `~` also returns you to your home directory
  - `cd` followed by `..` takes you up one directory level
- `ls` - Lists files in the current working directory.
  - often used with the following command line options
    - `-a` - All files
    - `-l` - Long listing (prints more details about the files)
- `top` or `htop` - A command line program for showing you running
  processes.  `htop` is a prettier nicer version of the regular top command.
- `ps` Lists running processes. Like top and htop, this lists out the processes running, but it's a little harder to use than those.
- `cp` and `mv` - Copies and moves files. You give these a source file and a destination file path. (Note, there is no rename command in unix, you just use `mv` to rename a file)
- `rm` - Removes a file. Be careful with this, there is no trash can for the command line.
  - `-f` Forces removal (be super careful when using this)
  - `-r` Remove recursively (Used to remove a heirarchy of files and folders)
  - `-v` Print out the files as they are bring removed
- `mkdir` and `rmdir` - Creates and removes a directory. Note: `rmdir` only works if the directory is empty, so you'll probably want to use `rm -r` to remove a folder recursively.
- `man` Look at the *manual* page for any command.  If you want to know more about the flags and options for a command, just type `man` followed by the command. Example: `man ls`

## Files

Unix is a file based operating system. Sometimes it's said that "In Unix, everything's a file".  Here's some handy tips about the kinds of files you will see in Unix.

If you do a `ls -al` on a folder you might see output similar to this:

```shell
drwxr-xr-x  8 user group 4096 Jan  1 00:00 .
drwxr-xr-x 48 user group 4096 Jan  1 00:00 ..
-rw-r--r-- 1  user group 1    Jan  1 00:00 .secret.txt
-rw-r--r-- 1  user group 1    Jan  1 00:00 README.md
```

let's break down what this showing us, there are 4 `files` here.
Some of these represent directories though, you can tell because the first character of the line is `d` for directory and `-` for a
regular file.

the directories `.` and `..` represent the current directory, and the parent directory of the current working directory.

The file `.secret.txt` is a *hidden* file. Files that start with a period are considered hidden in Unix. This means if we use `ls` without the `-a` option, we won't see those files.

All those `r`, `w`, and `x` letters are the permissions of the files.

- `r` - Read access
- `w` - Write access
- `x` - Executable access (we can run it as a program or in the case of directories we can navigate into it.)

There's three sections of them, `(rwx)(rwx)(rwx)`.

- User Permissions - What the owner of the file can do
- Group Permissions - What the group that owns the file can do
- Other Permissions - What everyone else can do.

The next field is the number of hard links, this isn't really that
useful to know and can mostly be ignored.

Then we have the owner of the file, followed by the group that owns the file.

Then the size of the file in bytes, followed by the time the file was last modified.

And finally the filename itself.

Or broken down into table form, like this

| Permissions | Links | Owner | Group | Size |  Date Modified | Filename |
|--|--|--|--|--|--|--|
|drwxr-xr-x| 8 |user| group |4096 |Jan  1 00:00 |.|
|drwxr-xr-x| 48 |user| group |4096 |Jan  1 00:00 |..|
|-rw-r--r--| 1  |user| group |1    |Jan  1 00:00 |.secret.txt|
|-rw-r--r--| 1  |user |group| 1 |   Jan  1 00:00 |README.md|
