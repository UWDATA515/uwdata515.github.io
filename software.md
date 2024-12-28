---
layout: page
title: Software
collection: winter2025
---

The course makes use of a number of software packages that students will install on their computers.
The following software are available for Windows, Mac, and Linux.

**Please try to install all of this software on your computer before the first day of class.**

## 1. Ensure you have access to a Unix-style terminal.

### MacOS and Linux operating systems

Use your operating system's program search (MacOS: spotlight search, Cmd-Space. Ubuntu: Ubuntu button in upper-left corner) up and search for `Terminal`.

You should get a window with a command prompt. Command prompt might have different words / characters, followed by a `$` and cursor for text input. Late 2018 and newer MacOS computers default to `zsh` instead of `bash`. This difference will briefly be covered in class, but you can run `bash` [+ Enter] in the terminal if you choose to use that instead.

### Windows 11 and Windows 10, version 1607+ (Windows Linux Subsystem)

All Windows users should note that the Windows command lines, cmd and PowerShell, differ greatly from the ``bash`` or ``zsh`` command prompt that software developers commonly use. From here on out, we will use "terminal" to refer to the Unix-style unless clearly and explicitly stated otherwise.

Note: Windows Linux Subsystem (WSL2 or the older WSL) is preferred over older Git Bash solution below. It's faster, more similar to what you'll see in class and has a more complete set of Unix programs.

Before trying the suggestions below, try opening the Windows Store (from your start menu) and search for Ubuntu 22.04.  It will be a free download and installing it "will just work" for most recent versions of Windows 11 on relatively new hardware. 

If installing from the Windows Store does not work, we suggest following these instructions for [installing a WSL distribution](https://learn.microsoft.com/en-us/windows/wsl/install).

Some tips:
* We highly suggest using the Ubuntu 22.04 distribution. Ubuntu is one of the more beginner-friendly Linux distros and the instructor is also able to record screen captures for this setup.
* We suggest setting your Linux distribution username and password to match your Windows ones. This will reduce confusion!

## 2. Ensure that Git is installed.

Type `git --version` into the terminal. If the terminal prints out any version number, you are successful. For example, my Macbook Pro returns `git version 2.24.1 (Apple Git-126)` and my Windows 10 WSL system returns `s`. You MUST have git working on your terminal for this course. Please come into office hours if you can't get it to work.

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

Also create a Github.com username. This is a free account. We will discuss more on the Version Control I lecture.

## 3. Installing Python via Anaconda / Miniconda
We recommend that you use the most recent version of Python 3.  Earlier versions of Python 3 work as well.  There are some differences between Python 2 and Python 3, and many systems only include Python 2.7 as a standard installation.  A Python installation for this course will be managed by the [conda](https://conda.io/docs/) package management system, described below.

Anaconda is a system for installing and otherwise managing Python and other software packages. Anaconda installs  See [http://conda.pydata.org/miniconda.html](http://conda.pydata.org/miniconda.html) for instructions for downloading and installing miniconda for your OS, selecting the Python 3 series installer.

**Windows users: please make sure to install Miniconda on your WSL instance, NOT just your Windows computer, so that you have access to it from within WSL. Follow the command-line instructions for a Linux instance.**

Below are detailed instructions **after** you have installed Miniconda (or the full Anaconda):
1. Update conda's listing of packages for your system: $``conda update conda``
2. Install Jupyter notebook and its requirements: $``conda install jupyter notebook``
3. Test that Jupyter notebooks run using the terminal to start the notebook: $``jupyter notebook``

If everything has worked correctly, it should print a URL to the console that opens an empty notebook. Depending on settings, it may automatically open the notebook server in your default browser.

## 4. Install a terminal text editor.
We highly suggest installing Nano, an easy to use text editor in the terminal.

### Linux operating systems (including WSL and Git Bash on Windows!)
For Ubuntu distributions, try $`sudo apt-get install nano`. For others, $`yum install nano`.

### MacOS operating system:
MacOS doesn't have a pre-installed package manager for their Unix programs. The best option is Homebrew with [full instructions on the website](https://brew.sh/).

Students can also select a graphical text editor of their choice, such as Notebook (Windows), vim (all platforms), Sublime (all platforms), or Visual Studio Code (all platforms). A text editor is different from word processing programs, like MS Word, in that text editors often recognize program syntax and do no formatting.

If you'd also like a graphical text editor but don't already have a favorite, we recommend installing either [atom](http://atom.io/) or [Sublime](http://www.sublimetext.com/), which are both available for all platforms.

## 5. Setting Up GitLab 
We will be using GitLab to submit homework and give feedback. GitLab is a web-based git hosting service that is similar to GitHub but hosted locally by the Computer Science Department. 

These steps are error-prone and hard to get right the first time. Please ask for help if you get stuck!

### Generating an SSH key 
Before you can clone from GitLab, you will need to create an SSH key. SSH is a protocol supported by git to access GitLab securely and without password authentication.

You might be able to skip this entire section if you have already done this for another course. To check if you already have a key generated:

1. Open a terminal and run the following command: ``ls ~/.ssh``
1. If you see a file called `id_ed25519.pub` or `id_rsa.pub`, that is your public SSH key. You can now proceed to the next section. Otherwise, continue on.

To generate a new SSH key:

1. Open your terminal and run the following command: ``ssh-keygen -t ed25519``
1. Next, you will be prompted to input a file path to save your SSH key pair to. If you don’t already have an SSH key pair, use the suggested path by pressing ``Enter``. Using the suggested path will normally allow your SSH client to automatically use the SSH key pair with no additional configuration.
1. Once the path is decided, you will be prompted to input a password to secure your new SSH key pair. It’s not required. If you don’t want to enter your password every time you use Git, you can skip creating it by pressing ``Enter`` twice.

### Adding SSH to your GitLab account
If you are using GitLab for the first time, you will need to submit your SSH key. To do this, follow these steps: 

1. Open a terminal and execute (replace with `id_rsa.pub` if needed): ``cat ~/.ssh/id_ed25519.pub``
   This will print out the public key that you just generated.
1. Visit GitLab’s SSH key management page by going to https://gitlab.cs.washington.edu/-/profile/keys. Paste your key into the box, and the rest of the fields should be filled in automatically. Press ``Add key``.
1. In the terminal, run ``ssh -T git@gitlab.cs.washington.edu`` to ensure that your key is correctly set up. You should receive a welcome message and should not be prompted for a password.
