# Installing [Homebrew]

[Homebrew] is a piece of software used on macOS to install additional unix command
line tools.  Homebrew can also be used to install regular mac apps via a mechanism
called Homebrew cask. But before we can do any of that, we need to install Homebrew
itself.

Now copy this command to your clipboard and paste it into the terminal and hit enter. This will avoid making a typo. Computers are very picky at the command line, and a single typo could make the entire process fail in some way.

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Homebrew will then start cloning it's files to your hard drive. Once it's installed you should get your shell prompt back so you can type more commands.

Homebrew will prompt you for your password, just type in your macOS password here and press enter.
(The terminal doesn't print out anything when you type a password in, but is it taking your password nonetheless)

Once this is finished, move on to [Installing Ansible]

[Installing Ansible]:ansible-setup.md
[Homebrew]:https://brew.sh
