# macOS Developer Setup Guide

macOS is an operating system built ontop of Unix, so installing all the software
you need is an easy task. Just follow the steps below and you'll be up an running
in no time.

## Supported macOS versions

You must have at least macOS Catalina to follow the instructions below. Older macOS
versions may work but haven't been tested. You can find your macOS version by
going to the Apple menu and choosing "About this mac".

## [Unix Terminology]

You may want to read about certain [Unix Terminology] that you will need to be familar with as a developer before continuing.

## The Terminal app

Most of the setup happens inside the macOS Terminal app.

Open the macOS Terminal app (Located in the 📁Utilities folder under the 📁Applications Folder on your main drive)

You should see your command prompt. It will either end in a `$` or a `%` character (depending on the version of macOS)

You'll also note, it'll display the `~` (tilde) character. In unix, the `~`
represents your home directory.

> Note: the difference between $ and % is which *[shell]* the operating system
> comes with by default... older macOS version came with the **[Bourne Again Shell]** ([bash])
> while newer macOS versions include the **[Z Shell]** ([zsh]).
> Once you finish these instructions you will have zsh no matter which version
> of macOS you have.

Once you've read about all the Unix terminology and have the terminal app open, move on to [Installing Xcode Command line tools]

[shell]:https://en.wikipedia.org/wiki/Shell_%28computing%29
[Ansible]:https://ansible.com
[Unix Terminology]:../resources/unix-terminology.md
[Bourne Again Shell]:https://www.gnu.org/software/bash/
[bash]:https://www.gnu.org/software/bash/
[Z Shell]:https://www.zsh.org/
[zsh]:https://www.zsh.org/
[Installing Xcode Command line tools]:xcode-command-line-tools-setup.md
