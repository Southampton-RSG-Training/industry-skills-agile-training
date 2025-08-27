---
title: Setup
---

## Data Sets

We will use the 'Coffee Ratings Dataset' throughout this training course.  

You can download this dataset in csv format from here: [full_dataset_coffee_ratings.csv](../episodes/data/full_dataset_coffee_ratings.csv)

This dataset was obtained from the TidyTuesday GitHub.  TidyTuesday is a weekly social data project and is organised by the Data Science Learning Community.

The data comes from the [Coffee Quality Database](https://github.com/jldbc/coffee-quality-database) courtesy of Data Scientist James LeDoux. These data were collected from the Coffee Quality Institute's review pages in January 2018.

There is data for both Arabica and Robusta beans, across many countries and professionally rated on a 0-100 scale. There are ratings for lots of different variables such as acidity, sweetness, fragrance, balance, etc.



## Software Setup

Please open the dropdown for your operating system and follow the setup instructions.  Then, look below the dropdowns and follow the 'Additional Git Setup' instructions too.

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

### Additional Git Setup

#### Setting up Git

The first time we use Git on a new machine, we need to configure it. We’re going to set some global options, so when Git starts tracking changes to files it records who made them and how to contact them.

(Please use your own name and the email address you used to sign up to GitHub!)

```bash
git config --global user.name "Firstname Surname"
git config --global user.email "fsurname@university.ac.uk"

```

We’re going to set Nano, a simple, minimal command-line text editor to be the default for when you need to edit messages.  If you’re already comfortable with another command-line editor, feel free to select that!

```bash
git config --global core.editor "nano -w"`
```

The three commands above only need to be run once: the flag --global tells Git to use the settings for every project on this machine.

You can check your settings at any time:

```bash
 git config --list
```

#### GitHub

We’ll be using the website [GitHub](https://github.com/) to host, back up, and distribute our code. You’ll need to create an account there. As your GitHub username will appear in the URLs of your projects there, it’s best to use a short, clear version of your name if you can.

#### SSH Key Setup

We’ll need to set up SSH access to GitHub from your computer. This is how GitHub checks your identity when you try to access it - and is more secure than a password. To set up SSH access, we generate a pair of keys - one public, one private. We want to add the public key to GitHub, whilst the private one stays on our computer.

We can run a simple command to generate a new SSH key. It’ll ask you for some settings, but you should just hit enter to use the defaults for everything:

```bash
ssh-keygen -t ed25519
```

```output
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/smangham/.ssh/id_ed25519): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in id_ed25519
Your public key has been saved in id_ed25519.pub
The key fingerprint is:
SHA256:tm2lRVXqWdkwiu+fvOF8WxRaf6peAqZHKSaWDO8jjjs user-name@computer-name
The key's randomart image is:
+--[ED25519 256]--+
|              +..|
|           . o +o|
|    .     . o .+o|
|     + .   + .ooo|
|      * S = +.o +|
|     o + B *   o.|
|    . o o = o + .|
|  Eo . . o   O oo|
|  oo.      .o B+.|
+----[SHA256]-----+
```

Now we’ve generated a key, we can add this to [GitHub](https://github.com) and register the key there. First, visit GitHub, and make sure you’ve signed in to your account. Once you’re signed in, go to [GitHub > Settings > SSH and GPG keys > Add new](https://github.com/settings/ssh/new), and you should see this:

![](../episodes/fig/add-ssh-key.png)

We need to fill in the details. Give the key a title like “Laptop SSH key”, and then paste your public key into the key box - we can find it in our ~/.ssh folder:

```bash
ls ~/.ssh
```

```output
id_ed25519  id_ed25519.pub  known_hosts
```

You want to copy the contents of the .pub file, which you can display with:

```bash
cat ~/.ssh/id_ed25519.pub
```

```output
ssh-ed25519 <SNIPPED FOR SECURITY> user-name@computer-name
```

**Make sure you copy the .pub file and not the private key!** Your private key lives on your machine and is never shared with anyone else. Then click Add key, and you’re done!


