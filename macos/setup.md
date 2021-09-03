# macOS Developer Setup Guide

macOS is an operating system built ontop of Unix, so installing all the software
you need is an easy task. Just follow the steps below and you'll be up an running
in no time.

## Supported macOS versions

You must have at least macOS Catalina to follow the instructions below. Older macOS
versions may work but haven't been tested. You can find your macOS version by
going to the Apple menu and choosing "About this mac".

## Unix terminology

Unix has it's own terms you might not be familiar with if you've only used
graphical operating systems with icons, draggable windows and a mouse pointer.

Here's some common ones you may hear:

- [Terminal] - A text based interface for interacting with your computer. This is
based on actual pieces of hardware that used to exist for connecting to a remote computer. Today we primarily mean an application which *emulates* one of these terminals. This means terminal applications are often called "Terminal Emulators"
- [Shell] - Distinct from terminal this is usually the default program running when you first open the terminal. It accepts input from the user, and can do things like run programs, navigate your files.
- [Filesystem] - This is just fancy word for "Folder Hierarchy".  On your computer
there's a hierarchy of folders, the Filesystem is a word used to describe the system that keeps track of all the folders and files on your system
- [Directory] - This is just the unix line word for "Folder". It literally means the same thing.

## The terminal app

Most of the setup happens inside the macOS Terminal app.

Open the macOS Terminal app (Located in the Utilities folder under the Applications Folder on your main drive)

You should see your command prompt. It will either end in a `$` or a `%` character (depending on the version of macOS)

You'll also note, it'll display the `~` (tilde) character. In unix, the `~`
represents your home directory.

> Note: the difference between $ and % is which *[shell]* the operating system
> comes with by default... older macOS version came with the **Bourne Again Shell** (bash)
> while newer macOS versions include the ***Z Shell** (zsh).
> Once you finish these instructions you will have zsh no matter which version
> of macOS you have.

## Installing the Xcode command line tools

Apple has a development tool called Xcode which is used to develop native
apps for macOS, iOS, and iPadOS. We don't need Xcode itself, but we do need
the Xcode command line tools, which includes a C compiler and some other tools.

Type or copy and paste this command exactly like this into the terminal and press enter:

```sh
xcode-select --install
```

This should trigger a dialog box to appear asking if you want to install the
command line tools, click Ok and wait for the tools to finish installing.

## Installing [Homebrew]

[Homebrew] is a piece of software used on macOS to install additional unix command
line tools.  Homebrew can also be used to install regular mac apps via a mechanism
called Homebrew cask. But before we can do any of that, we need to install Homebrew
itself.

Now copy this command to your clipboard and paste it into the terminal and hit enter. This will avoid making a typo. Computers are very picky at the command line, and a single typo could make the entire process fail in some way.

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Homebrew will then start cloning it's files to your hard drive. Once it's installed you should get your shell prompt back so you can type more commands.

## [Ansible] installtion

This guide uses [Ansible](https://ansible.com) to automate installation of the
development tools you'll need.

So first thing we should do is to install ansible.

We use python's `pip3` tool to do this, since ansible is written in python.

Run this command at the shell prompt.

```sh
pip3 install ansible
```

Once it has successfully installed, your shell prompt should reappear.

## Ansible Playbook

Now we are going to clone the ansible playbook down so that ansible can
install all of our development tools.

We will use `git` to clone it to a folder on our computer.

At the shell prompt type the following command.

```sh
git clone https://github.com/bartdorsey/developer-playbook.git
```

Once this finished, there will be a new folder called "developer-playbook" created
in your home directory.

type `ls -l` and you should see this folder in the list

We need to navigate to this folder in the shell. We use the `cd` command to
move around our computer's folder heirarchy (often called a file system)

```sh
cd developer-playbook
```

You will notice your shell prompt changes to indicate you are now *in* the `developer-playbook` folder. Run `ls -l` again and you'll see the list of files
in this folder.

The file we are interested in is `variables-example.yml`

We need to open this file in an editor and change a few things. We'll be editing
files a lot in this class, and we'll usually use [Visual Studio Code] by Microsoft
to edit our code files. If you have VSCode already installed, you can use it to
edit this file, but for now, we can use a handy terminal based editor called `nano`.

First, we should copy this example file to the real file using the `cp` command.

```sh
cp variables-example.yml variables.yml
```

This makes a copy of the example file and names it `variables.yml`

Now edit it with nano (or your editor of choice)

```sh
nano variables.yml
```

In nano, you can use the arrow keys to move around in the file and type to change
things.  However you'll notice you can't move the cursor by clicking the mouse.
This is a terminal application! Keyboard only!

In any case, you'll want to edit the two lines in here:

```text
git_user: 'Change Me'
git_email: 'change@changeme.com'
```

Chane the user to your full name, and the email to your email address.

Then look at the bottom of nano, you'll see there's a bunch of keyboard shortcuts.

The `^` character means the control key, so use `^X` (Control-X) to exit.

Nano will ask you if you want to save the buffer (nano-speak for file) and what
filename you want, just keep it named `variables.yml`

## Running the playbook

Now we can run the following command to run the ansible playbook.

```sh
ansible-playbook -K playbook.yml
```

The first thing the playbook does is ask you for a `BECOMES` password.  This is
because ansible needs to `BECOME` the superuser in order to install some of the
software. Just type your macOS password here and press enter.

Then ansible attempts to install all the software, Sit back and relax, this could
take a while.

Once this is finished you will have the following pieces of software installed on
your mac:

In your /Applications folder:

- [Visual Studio Code] - A code editor
- [Postico] - A graphical user interface (GUI) for browsing your PostgreSQL database
- [Postbird] - An alternative GUI for Postgres
- [Insomnia] - An application for testing APIs

At the command line:

- [zsh] - If you didn't already have it, your default shell will now be zsh.
- [nvm] - The node version manager, a program to help you manage different node
versions
- [Node.JS] - A JavaScript code runner, we'll be using this to run our JavaScript
- [zip and unzip] - Command line utilities to compress and uncompress zip files.
- [htop] - A nice way to view all the programs running on your computer from the terminal
- [pgcli] - A fancy postgres command line interface
- [starship] - A fancy replacment prompt which shows you lots of interesting information about your node version and information about your git repos.

And running as a background program:

- [PostgreSQL] - A database server we'll use to store data for our applications

## Restart your terminal

The last step is to close your terminal and reopen it, Once you've reopened it,
you should notice your prompt looks different. This is the starship prompt,
and shows you more information than just the folder you are in.

## Errors

If you run into any error messages during the setup, please reach out to an
instructor for additional help.

[Homebrew]:https://brew.sh
[shell]:https://en.wikipedia.org/wiki/Shell_%28computing%29
[Ansible]:https://ansible.com
[Visual Studio Code]:https://code.visualstudio.com/
[Postico]:https://eggerapps.at/postico/
[Postbird]:https://github.com/Paxa/postbird
[Insomnia]:https://insomnia.rest/
[zsh]:https://www.zsh.org/
[nvm]:https://github.com/nvm-sh/nvm
[Node.JS]:https://nodejs.org/en/
[htop]:https://htop.dev/
[pgcli]:https://www.pgcli.com/
[starship]:https://starship.rs
[PostgreSQL]:https://www.postgresql.org/
[zip and unzip]:http://infozip.sourceforge.net/
