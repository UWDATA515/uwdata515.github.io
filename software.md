---
layout: page
title: Software
collection: winter2027
---

The course makes use of a number of software packages that students will install on their computers.
The following software are available for Windows, Mac, and Linux.

**Please try to install all of this software on your computer before the first day of class.**

If you took DATA 598B in Autumn, you will already have everything set up.

## 0. Connect to the `eduroam` Wi-Fi network

For this class, you may have trouble using the `University of Washington` Wi-Fi network to do all activities. Instead, we *strongly* recommend that you be connected to `eduroam`. For instructions on how to connect to `eduroam`, follow the “How to access the eduroam network” section on [this page](https://uwconnect.uw.edu/it?id=kb_article_view&sysparm_article=KB0034255#howtouse).

## 1. Ensure you have access to a Unix-style terminal.

### MacOS and Linux operating systems

Use your operating system's program search (MacOS: spotlight search, Cmd-Space. Ubuntu: Ubuntu button in upper-left corner) up and search for `Terminal`.

You should get a window with a command prompt. Command prompt might have different words / characters, followed by a `$` and cursor for text input. Late 2018 and newer MacOS computers default to `zsh` instead of `bash`. This difference will briefly be covered in class, but you can run `bash` [+ Enter] in the terminal if you choose to use that instead.

### Windows 11 and Windows 10, version 1607+ (Windows Linux Subsystem)

All Windows users should note that the Windows command lines, cmd and PowerShell, differ greatly from the ``bash`` or ``zsh`` command prompt that programmers commonly use. From here on out, we will use "terminal" to refer to the Unix-style unless clearly and explicitly stated otherwise.

Before trying the suggestions below, try opening the Windows Store (from your start menu) and search for Ubuntu 26.04.  It will be a free download and installing it "will just work" for most recent versions of Windows 11 on relatively new hardware. 

If installing from the Windows Store does not work, we suggest following these instructions for [installing a WSL distribution](https://learn.microsoft.com/en-us/windows/wsl/install).

Some tips:
* We highly suggest using the Ubuntu 26.04 distribution (as of 2027). Ubuntu is one of the more beginner-friendly Linux distros. Any of the LTS ("Long-Term Support") versions should work, however - this includes 26.04, 24.04, and 22.04 (as of 2027).
* We suggest setting your Linux distribution username and password to match your Windows ones. This will reduce confusion!

## 2. Ensure that Git is installed.

Type `git --version` into the terminal. If the terminal prints out any version number, you are successful. For example, my Macbook Pro returns `git version 2.50.1 (Apple Git-155)`. You MUST have git working on your terminal for this course. Please come into office hours if you can't get it to work.

### Mac OS Note: Some students reported an error with ``git``:
```
xcode-select: note: no developer tools were found at
'/Applications/Xcode.app', requesting install. Choose an option
in the dialog to download the command line developer tools.
```
To fix this, do the following:

* Start a new Terminal
* Run the following command: ``xcode-select --install``
* Click ``Install``
* Click ``Agree`` to agree to the terms
For more information see this [link](http://mac-how-to.wonderhowto.com/how-to/install-command-line-developer-tools-without-xcode-0168115/)

### Github.com

Also create a Github.com username. This is a free account. We will discuss more in lecture.

## 3. Install a terminal text editor.
We highly suggest installing Nano, an easy to use text editor in the terminal. If you are familiar with another text editor, such as emacs or vi, then feel free to use that instead.

You might already have Nano installed. To check, enter $`nano -version` in the Terminal. If you get a version number back, for example `Nano 8.6`, then you have Nano installed. Nano is not installed if you get an error message saying: `command not found: nano`.

Note that some users have reported that on Windows using WSL they need to use $`nano --version` instead.

Note that on macOS, your Nano version will likely return a version of Pico, for example `Pico 5.06`. For the purposes of this course, Pico and Nano are identical terminal text editors.

### Installing Nano on a Linux operating system (including WSL)
For Ubuntu distributions, try `sudo apt-get install nano`. For others, $`yum install nano`.

### Installing Nano on the MacOS operating system
MacOS doesn't have a pre-installed package manager for their Unix programs. The best option is Homebrew with [full instructions on the website](https://brew.sh/). You can also choose to use [MacPorts](https://www.macports.org/install.php).

Once installed, download Nano with the following command in your terminal:
* `brew install nano` if using Homebrew
* `sudo port install nano` if using MacPorts

## 4. Installing Python via Anaconda / Miniconda
We recommend that you use the most recent version of Python 3.  Slightly earlier versions of Python 3 work as well.  A Python installation for this course will be managed by the conda package management system, described below.

Conda is a system for installing and otherwise managing Python and other software packages. For data science purposes, conda is a great tool for administering complex, potentially multi-language projects.

We recommend that you install conda from the open source community managed conda distribution because they offer terms of service that best align with academic research. The installers are available `here`[https://github.com/conda-forge/miniforge], scroll down to the Install heading and follow the directions for “Unix-like platforms” (Windows users will be installing this using their WSL bash terminal). Let it install in the default location and answer “yes” to the installer question about initializing conda.

**Windows users: please make sure to install conda on both your Windows computer AND your WSL instance, NOT just your Windows computer, so that you have access to it from within WSL. Follow the command-line instructions for a Linux instance.**

Below are detailed instructions **after** you have installed conda:
1. Update conda's listing of packages for your system: $``conda update conda``
2. Install Jupyter notebook and its requirements: $``conda install jupyter notebook``
3. Test that Jupyter notebooks run using the terminal to start the notebook: $``jupyter notebook``

If everything has worked correctly, it should print a URL to the console that opens an empty notebook. Depending on settings, it may automatically open the notebook server in your default browser.

## 5. Setting Up GitLab 
We will be using GitLab to submit some homework and give feedback. GitLab is a web-based git hosting service that is similar to GitHub but hosted locally by the Computer Science Department. 

These steps are error-prone and hard to get right the first time. Please ask for help if you get stuck!

### Generating an SSH key 
Before you can clone from GitLab, you will need to create an SSH key. SSH is a protocol supported by git to access GitLab securely and without password authentication.

You might be able to skip this entire section if you have already done this for another course. To check if you already have a key generated:

1. Open a terminal and run the following command: `ls ~/.ssh`
1. If you see a file called `id_ed25519.pub` or `id_rsa.pub`, that is your public SSH key. You can now proceed to the next section. Otherwise, continue on.

To generate a new SSH key:

1. Open your terminal and run the following command: `ssh-keygen -t ed25519`
1. Next, you will be prompted to input a file path to save your SSH key pair to. If you don’t already have an SSH key pair, use the suggested path by pressing `Enter`. Using the suggested path will normally allow your SSH client to automatically use the SSH key pair with no additional configuration.
1. Once the path is decided, you will be prompted to input a password to secure your new SSH key pair. It’s not required. If you don’t want to enter your password every time you use Git, you can skip creating it by pressing `Enter` twice.

### Adding SSH to your GitLab account
If you are using GitLab for the first time, you will need to submit your SSH key. To do this, follow these steps: 

1. Open a terminal and execute (replace with `id_rsa.pub` if needed): `cat ~/.ssh/id_ed25519.pub`
   This will print out the public key that you just generated.
1. Visit GitLab’s SSH key management page by going to [https://gitlab.cs.washington.edu/-/user_settings/ssh_keys](https://gitlab.cs.washington.edu/-/user_settings/ssh_keys). Click `Add new key` and paste your key into the box, and the rest of the fields should be filled in automatically. Press `Add key`.
1. In the terminal, run `ssh -T git@gitlab.cs.washington.edu` to ensure that your key is correctly set up. You should receive a welcome message and should not be prompted for a password.

### Set up your shell for git
If you don't set your `$EDITOR` shell variable to nano, you may get stuck in a different text editor when you try to use git. Update the variable to nano:

```sh
$ EDITOR=/usr/bin/nano # or wherever your nano is on your system, use `which nano`
```

When you do this, the variable will only be updated for your **current terminal session**. If you'd like to make it permanent (and you should), then put the same command into your `~/.bashrc` file (or `~/.zshrc` file if you're using `zsh`). If you're not familiar with the rc files, you can read more [here](https://uw-msds-python.github.io/lectures/lecture02_scripting#bashrc).

## 6. Install a graphical text editor.

Students can also select a graphical text editor of their choice, such as Visual Studio Code (all platforms), Atom (all platforms), Sublime (all platforms), Notebook (Windows), or vim (all platforms). A text editor is different from word processing programs, like MS Word, in that text editors often recognize program syntax and do no formatting. The instructor in this course will be using Visual Studio Code (also known as VS Code), so if you don't have a preference, then we recommend installing it.

[Visual Studio Code (also known as VS Code)](https://code.visualstudio.com/download) is a graphical code editor that can be customized and extended with a vast library of open-source extensions. After installing VS Code, install [the Python extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python) and [the Jupyter extension](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter).

If you frequently use R, you can install [the R language extension too](https://marketplace.visualstudio.com/items?itemName=REditorSupport.r).

### Visual Studio Code with Windows Subsystem for Linux

If you are using Windows and WSL, you MUST install the WSL extension for Visual Studio Code. Without this extension, you will not be able to run Visual Studio Code from WSL. Install the extension [here from the Extension Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl).

If you ever want to open a particular directory in Visual Studio Code from your WSL instance, navigate to that directory in the WSL terminal and type `code .` to open Visual Studio Code.

Whenever you run Visual Studio Code from WSL, you should see a small rectangle in the bottom left corner of your window that says WSL; if you don’t see this indicator, it likely means you’re not in WSL:

![WSL indicator in VS Code](images/wsl-statusbar-indicator.png)
> Image credit: [https://code.visualstudio.com/docs/remote/wsl]([https://code.visualstudio.com/docs/remote/wsl)
