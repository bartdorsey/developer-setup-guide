# [Ansible] installation

This guide uses [Ansible](https://ansible.com) to automate installation of the
development tools you'll need.

The ansible playbook we've created installs the following tools:

In your Applications folder:

- [Visual Studio Code] - A code editor
- [Postico] - A graphical user interface (GUI) for browsing your PostgreSQL database
- [Postbird] - An alternative open source GUI for Postgres
- [Insomnia] - An application for testing APIs

At the command line:

- [zsh] - If you didn't already have it, your default shell will now be zsh.
- [nvm] - The node version manager, a program to help you manage different node
versions
- [Node.JS] - A JavaScript code runner, we'll be using this to run our JavaScript
- [zip and unzip] - Command line utilities to compress and uncompress zip files.
- [htop] - A nice way to view all the programs running on your computer from the terminal
- [pgcli] - A fancy postgres command line interface
- [starship] - A fancy replacment shell prompt which shows you lots of interesting information about your node version and information about your git repos.

And running as a background program:

- [PostgreSQL] - A database server we'll use to store data for our applications

## Installation of Ansible

So first thing we should do is to install ansible.

We are going to use homebrew to install ansible.

Run this command at the shell prompt.

```sh
brew install ansible
```

Once it has successfully installed, your shell prompt should reappear and you can move on to [Running the Ansible Playbook]

[Running the Ansible Playbook]:../common/ansible-playbook-setup.md
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
