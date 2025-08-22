---
title: Setup
---

FIXME: Setup instructions live in this document. Please specify the tools and
the data sets the Learner needs to have installed.

## Data Sets

<!--
FIXME: place any data you want learners to use in `episodes/data` and then use
       a relative link ( [data zip file](data/lesson-data.zip) ) to provide a
       link to it, replacing the example.com link.
-->
FIXME: Download coffee beans dataset

## Software Setup

We’ll be using the website [GitHub](https://github.com/) to host, back up, and distribute our code. You’ll need to create an account there. As your GitHub username will appear in the URLs of your projects there, it’s best to use a short, clear version of your name if you can.

FIXME: git config

FIXME: ssh key setup

::::::::::::::::::::::::::::::::::::::: discussion

### Details

Setup for different systems can be presented in dropdown menus via a `spoiler`
tag. They will join to this discussion block, so you can give a general overview
of the software used in this lesson here and fill out the individual operating
systems (and potentially add more, e.g. online setup) in the solutions blocks.

:::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::: spoiler

### Windows

#### Open a Terminal

We’ll be using Git Bash. If you’ve already installed Git Bash then go to the next section. Otherwise, go to [git for windows](https://gitforwindows.org/) and click Download, then install it. Most of the options can be left on default, but be sure you check these:

-   **Choosing the default editor used by Git**: Make sure **Nano** is selected from the drop-down. If you’re comfortable with other editors, feel free to change it, but we recommend Nano - we use it as it’s present on Windows, Mac and Linux. If you change it, you might not quite match what we’re doing on-screen.
-   **Adjusting your PATH environment**: Make sure **Git from the command line and also from 3rd-party software** is selected.
-   **Choosing HTTPS transport backend**: Make sure **Use the native Windows Secure Channel Library** is selected.
-   **Configuring the terminal emulator to use with Git Bash**: Make sure **Use Windows’ default console window** is selected.

#### Git Setup

We’ll be using Git Bash for both git and a shell to run it in. 

#### Python

The “Anaconda3” package provides everything Python-related you will need for the workshop. To install Anaconda, follow the instructions below.

Download the latest Anaconda Windows installer from [Anaconda](https://www.anaconda.com/download), you may need click 'Get Started' and register first. 

Double-click the installer and follow the instructions. **When asked “Add Anaconda to my PATH environment variable”, answer “yes”. It will warn you not to, but it’s required for it to be found by git bash**. After it’s finished, close and reopen any open terminals to reload the updated PATH and allow the installed Python to be found.

Once the Anaconda installation is finished you will be asked if you want the installer to initialize Anaconda3 by running conda init? You should select yes. Alternatively/additionally you will need to run the following command in Git Bash

```bash
conda init bash
```
Then close and reopen GitBash.

Please test the python install open GitBash (or your favorite terminal) and run the following command to verify that the installation was successful.

```bash
cd ~
python
```
You can then type the following to exit:

```bash
quit()
```

**Git Bash might hang on this command and not launch the Python interpreter.** 
**In this case close and reopen git bash and issue the following commands:**

```bash
cd ~
echo 'alias python="winpty python.exe"' >> ~/.bash_profile
source .bash_profile
python
```

Note: for older versions of git bash you will need to use .bashrc rather than .bash_profile

::::::::::::::::::::::::

:::::::::::::::: spoiler

### MacOS

#### Open a Terminal

You can open a terminal by opening the “Terminal” application, which can be found in the “Utilities” folder which is in your “Applications” folder.

#### Git Setup

To use Git you must install the Apple Command Line Tools, this may take a few minutes.

You can obtain these [from Apple](https://idmsa.apple.com/IDMSWebAuth/signin.html?path=%2Fdownload%2Fall%2F%3Fname%3Dcommand%2520line%2520tools%2520for%2520xcode%252012&appIdKey=891bd3417a7776362562d2197f89480a8547b108fd934911bcbea0110d07f757&rv=0) (requires your Apple ID)

-   Select **Command Line Tools for Xcode 12 (or higher)** and click the link to download the dmg archive.
-   If prompted, choose to allow downloads from developer.apple.com
-   Open the downloaded dmg archive from the Downloads folder
-   Double-click the Command Line Tools.pkg icon to install

Alternatively, you can install the tools from the command line:

```bash
xcode-select --install
```
#### Python

-   **Mac OS Intel**: Download the latest Anaconda Mac OS X installer from [Anaconda](https://www.anaconda.com/download). Double-click the .pkg file and follow the instructions.
-   **Mac OS M1**: If you have a M1 Mac you need a specific version of Anaconda follow this link: [M1 Compatible Anaconda](https://repo.anaconda.com/archive/Anaconda3-2022.05-MacOSX-arm64.pkg).  Once the Anaconda installation is finished you will be asked if you want the installer to **initialize Anaconda3 by running conda init**? You should select **yes**.

::::::::::::::::::::::::


:::::::::::::::: spoiler

### Linux

#### Open a Terminal

This will depend on the Linux distribution you are running, but you should be able to find a “Terminal” application in your desktop’s application menu.

#### Git Setup

Git comes pre-installed on most Linux distributions. You can test if it’s installed by running `git --version`. If it’s not installed, you can install it by running `sudo apt-get install git` or `sudo yum install git`, depending on your distribution.

#### Python

Download the latest Anaconda Linux Installer from [Anaconda](https://www.anaconda.com/download).

Install via the terminal like this (you will need to change the version number to the latest version):

First move to the folder where you downloaded the installer, this is likely to be the Downloads folder e.g.

```bash
cd ~/Downloads
```

```bash
bash Anaconda3-2021.11-Linux-x86_64.sh
```

Answer ‘yes’ to allow the installer to initialize Anaconda3 in your .bashrc.
::::::::::::::::::::::::

