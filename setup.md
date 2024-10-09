---
title: Setup
---

Completing this course requires you to have access to a computer with Git
installed. This course is currently being delivered remotely so please make sure
you have access to a suitable computer. All attendees should download the zip
file and, if not already available, install Git.

## Downloading the Zip File

The zip archive containing files that will be used in the session is available
[here](code/recipe.zip). Please download and **save it in your home directory,
do not extract it yet**.

## Install Git

Please follow the relevant instructions depending on your operating system.

> ## Windows
>
> 1. Download the Git for Windows [installer](https://git-for-windows.github.io/).
> 1. Run the installer and follow the steps below:
>    1. Click on "Next" four times (two times if you've previously installed Git). You don't need to change anything in the Information, location, components, and start menu screens.
>    1. From the dropdown menu select "Use the nano editor by default" and click on "Next".
>    1. Select “Override the default branch name for new repositories” and use inclusive terms like “main” (Refer: [The new Git default branch name](https://about.gitlab.com/blog/2021/03/10/new-git-default-branch-name/))
>    1. Ensure that "Git from the command line and also from 3rd-party software" is selected and click on "Next". (If you don't do this Git Bash will not work properly, requiring you to remove the Git Bash installation, re-run the installer and to select the "Git from the command line and also from 3rd-party software" option.)
>    1. Ensure that "Use bundled OpenSSH" is selected and click on "Next".
>    1. Ensure that "Use the native Windows Secure Channel library" is selected and click on "Next".
>    1. Ensure that "Checkout Windows-style, commit Unix-style line endings" is selected and click on "Next".
>    1. Ensure that "Use Windows' default console window" is selected and click on "Next".
>    1. Ensure that “Fast-forward or merge” is selected and click on "Next".
>    1. Ensure that “Git Credential Manager” is selected and click on "Next".
>    1. Ensure that "Enable file system caching" is selected and click on "Next".
>    1. Ensure to select “Enable experimental built-in file system monitor” and click on "Install".
>    1. Click on "Finish".
> 1. If your "HOME" environment variable is not set (or you don't know what this is):
>    1. Open command prompt (Open Start Menu then type `cmd` and press [Enter])
>    1. Type the following line into the command prompt window exactly as shown: `setx HOME "%USERPROFILE%"`
>    1. Press [Enter], you should see `SUCCESS: Specified value was saved`.
>    1. Quit command prompt by typing `exit` then pressing [Enter]
>
> This will provide you with both Git and Bash via the program Git Bash. You
> should be able to launch Git Bash from the Start Menu. Within the window that
> launches enter the command `git --version` and press enter. You should see
> output similar to that below:
>
> ~~~ bash
> git version 2.40.0.windows-1
> ~~~
> {: .output}
{: .solution}

> ## macOS
>
> Apple provide a suite of UNIX-style command line tools that includes git. Install
> them by opening the "Terminal" app and running:
>
> ~~~ bash
> $ xcode-select --install
> xcode-select: note: install requested for command line developer tools
> ~~~
>
> This will open a dialog that asks for your confirmation to install the tools. If
> it does not open a dialog, it may be because it is already installed (the error
> message will be clear).
>
> To check the installation was successful open the "Terminal" app. In the window
> that launches enter the command `git --version` and press enter. You should see
> output similar to that below:
>
> ~~~ bash
> git version 2.37.1 (Apple Git-137.1)
> ~~~
> {: .output}
>
> **If the above does not work**, you may have and older version of macOS.
> Try the following: install Git for Mac by downloading and running the
> most recent "mavericks" installer from [this list](http://sourceforge.net/projects/git-osx-installer/files/). Because this
> installer is not signed by the developer, you may have to right click (control
> click) on the .pkg file, click Open, and click Open on the pop up window. After
> installing Git, there will not be anything in your `/Applications` folder, as
> Git is a command line program. **For older versions of OS X (10.5-10.8)** use
> the most recent available installer labelled "snow-leopard".
{: .solution}

> ## Linux
>
> If Git is not already available on your machine you can try to install it via
> your distribution's package manager. For Debian/Ubuntu run `sudo apt-get install
> git` and for Fedora run `sudo dnf install git`.
>
> To check the installation was successful open a new terminal. In the window that
> launches enter the command `git --version` and press enter. You should see
> output similar to the below:
>
> ~~~ bash
> git version 2.40.0
> ~~~
> {: .output}
{: .solution}

## Optional additional setup

### GitHub

This course will make use of [GitHub](https://github.com), an online repository hosting
site. If you do not already have a GitHub account, you may wish to create one ahead of
time, although this will be covered during the course.

Communicating with GitHub securely requires a means of
[authentication](https://docs.github.com/en/authentication). We will walk through
creating a personal access token (PAT) during the course, but you may wish to look at
this ahead of time. Alternatively, if you already have an SSH key, you may wish to add
this to your GitHub account.

### GitKraken

This course will demonstrate the use of [GitKraken](https://gitkraken.com/), a desktop
application for using git. There are a number of other similar applications, such as
GitHub Desktop, however, we will use GitKraken as it is cross-platform and therefore
accessible for all course attendees. If you already have a preferred desktop git
application, feel free to continue using that, but you may wish to compare the
functionality with your current choice.

{% include links.md %}
