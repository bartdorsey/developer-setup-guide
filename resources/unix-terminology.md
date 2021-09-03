# Unix terminology

Unix (and therefore Linux) has it's own terms you might not be familiar with if you've only used
graphical operating systems with icons, draggable windows and a mouse pointer.

Here's some common ones you may hear:

- [CPU] - Central Processing Unit - The chip which does all the calculations necessary for your computer to run programs.
- [RAM] - Random Access Memory. Computer chips which hold temporary information inside the computer while programs are running. Information in RAM is lost when the computer is off.
- [Program] - A piece of software, an "App" if you will, usually stored as a file, a set of instructions to make the computer do something.
- [Process] - A particular piece of software that is running and taking up space in your computer's RAM and executing instructions on your CPU.
- [Kernel] - The core part of the operation system responsible for managing all the programs running on the computer. This is the part of the system that is actually Linux. The kernel of macOS is called [XNU]
- [Storage] - Also called Disks or Mass Storage, a permanent place to store information inside a computer. Information in Storage is retained even when the computer is off.
- [Filesystem] - This is just fancy word for "Folder Hierarchy". On your computer
  there's a hierarchy of folders, the Filesystem is a word used to describe the system that keeps track of all the folders and files on your system, this is sometimes used interchangably with the term [Storage] or Disk.
- [Directory] - This is just the unix word for "Folder". It literally means the same thing.
- [Path] - A way of writing out where a certain folder or file is within the Filesystem. On Unix systems each folder or file is separated by the `/` (forward slash) character
- [Terminal] - A text based interface for interacting with your computer. This is
  based on actual pieces of hardware that used to exist for connecting to a remote computer. Today we primarily mean an application which _emulates_ one of these terminals. This means terminal applications are often called [Terminal Emulators]

    | An early terminal    | The macos Terminal App|
    |----------------------|-----------------------|
    | ![An early terminal] | ![macos terminal app] |

- [Shell] - Distinct from the terminal this is usually the default program running when you first open the terminal. It accepts input from the user, and can enter commands that will run other programs. The shell usually has it's own unique mini-programming language as well. Common shells are [bash] and [zsh]
- [Command] - the name of a program or alias we can type at the shell which performs some action
- [Command Arguments] - also called parameters, these are items passed to a command. Usually we separate them with spaces.
- [Command Options] - (also known as a flag, or switch) characters or words passed to a command which modify it's behavior. They usually start with a single hypen `-` for single letter options, or double hypens `--` for full word options.

  Here's an example command with some options and arguments.

      ls -l --all Documents

  | Command | Short Option | Long Option | Argument  |
  | ------- | ------------ | ----------- | --------- |
  | ls      | -l           | --all       | Documents |

- [Environment Variable] - A variable that is stored in RAM that is part of the operating system and not part of any particular program.
- [Home Directory] - The default directory for your user. It is represented
  by the shorthand `~` (tilde) character. On Linux it is usually in the path `/home/username`, on macOS it is usually `/Users/username`
- [Root Directory] - The top level parent of all folders in the Filesystem. Usually represented by the `/` character.
- [Root user] - Also known as the super user and not to be confused with the root directory, this is an administrative user on Unix systems that can do anything. Your regular user account is restricted to prevent you from messing up important system files.
- [sudo] - Pronounced "soo-doo" This stands for "Super User Do". It allows us to run a command as the [Root user]. We usually need this when installing software system-wide or editing system files. We prefix our normal command with `sudo` to use it.
- [Package Manager] - A piece of software on a unix system to manage the installation of software. On Ubuntu Linux this is "Advanced Package Tool" ([apt]), on macOS a popular choice is [Homebrew]

[cpu]: https://en.wikipedia.org/wiki/Central_processing_unit
[ram]: https://en.wikipedia.org/wiki/Random-access_memory
[storage]: https://en.wikipedia.org/wiki/Mass_storage
[program]: https://en.wikipedia.org/wiki/Computer_program
[process]: https://en.wikipedia.org/wiki/Process_(computing)
[environment variable]: https://en.wikipedia.org/wiki/Environment_variable
[home directory]: https://en.wikipedia.org/wiki/Home_directory
[filesystem]: https://en.wikipedia.org/wiki/File_system
[directory]: https://en.wikipedia.org/wiki/Directory_(computing)
[terminal emulators]: https://en.wikipedia.org/wiki/Terminal_emulator
[terminal]: https://en.wikipedia.org/wiki/Computer_terminal
[path]: https://en.wikipedia.org/wiki/Path_(computing)
[root directory]: https://en.wikipedia.org/wiki/Root_directory
[shell]: https://en.wikipedia.org/wiki/Shell_%28computing%29
[root user]: https://en.wikipedia.org/wiki/Superuser
[sudo]: https://en.wikipedia.org/wiki/Sudo
[package manager]: https://en.wikipedia.org/wiki/Package_manager
[apt]: https://en.wikipedia.org/wiki/APT_(software)
[command]: https://en.wikipedia.org/wiki/Command_(computing)
[command arguments]: https://en.wikipedia.org/wiki/Command-line_interface#Arguments
[command options]: https://en.wikipedia.org/wiki/Command-line_interface#Command-line_option
[homebrew]: https://brew.sh
[kernel]: https://en.wikipedia.org/wiki/Kernel_(operating_system)
[xnu]: https://en.wikipedia.org/wiki/XNU
[linux]: https://www.kernel.org/
[an early terminal]: https://upload.wikimedia.org/wikipedia/commons/thumb/9/9f/DEC_VT100_terminal_transparent.png/270px-DEC_VT100_terminal_transparent.png
[macos terminal app]: https://upload.wikimedia.org/wikipedia/commons/thumb/7/78/Appleterminal2.png/320px-Appleterminal2.png
[bash]: https://www.gnu.org/software/bash/
[zsh]: https://www.zsh.org
