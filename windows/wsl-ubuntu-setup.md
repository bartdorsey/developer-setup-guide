# Install WSL and Ubuntu

Now it's time to install WSL and Ubuntu.

Type the following into the powershell prompt exactly and hit enter:

```powershell
wsl --install -d Ubuntu
```

This will download and install WSL, the WSL Linux Kernel and Ubuntu.

![wsl Ubuntu Install Step 1](images/wsl-ubuntu-install-step1.png)

Once it finishes, close Powershell and **restart** your computer.

After a reboot, the setup of Ubuntu will continue, you will see powershell reopen.

![powershell Ubuntu Step 2](images/powershell-ubuntu-step2.png)

and then an "Ubuntu" window opens and installs Ubuntu (this step might take a while)

It will prompt you for your username.  You can make this whatever you would like.

Remember this is a new *virtual computer*, it has it's own username and it's own password. So don't forget it!

![Ubuntu install step 3](images/ubuntu-install-step3.png)

Once Ubuntu is finished, you should see the Ubuntu terminal prompt.

![Ubuntu installed](images/ubuntu-installed.png)

Once you've got the Ubuntu Terminal prompt, Move on to [Installing Windows Terminal]

[Installing Windows Terminal]:windows-terminal-setup.md
