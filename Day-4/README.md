🐧 Day 4: Package Management

## Today's Objective
To learn the full cycle of finding, installing, updating, and removing software using the Advanced Package Tool (apt).

## Key Learnings
Package Manager: I learned that apt is the command-line tool used on Debian-based systems like Ubuntu to handle software. It automates the entire process, including fetching files, installation, configuration, and removal.

Repositories: Software is stored in online repositories. The package manager knows how to securely connect to these repositories to get the software.

update vs. upgrade: This was a key distinction. sudo apt update doesn't install new software; it just downloads the latest list of available packages from the repositories. sudo apt upgrade is what actually installs the new versions of the packages I already have.

Dependencies: The best part is that apt automatically handles dependencies. If a program I want to install needs another library to work, apt installs it for me.

sudo apt update
sudo apt upgrade
apt search
sudo apt install
sudo apt remove
sudo apt autoremove

## Task Walkthrough: Installing and Removing htop
Today's task was to go through the full lifecycle of a package using the htop utility, a great improvement over the standard top command.

1. Update Package Lists:
First things first, I synchronized my local package list with the online repositories.

Bash

$ sudo apt update
Hit:1 http://in.archive.ubuntu.com/ubuntu jammy InRelease
Get:2 http://in.archive.ubuntu.com/ubuntu jammy-updates InRelease [119 kB]
...
Fetched 2,333 kB in 2s (1,135 kB/s)
Reading package lists... Done
2. Search for the Package:
I wanted to make sure I had the right name for the package, so I used apt search.

$ apt search htop
Sorting... Done
Full Text Search... Done
htop/jammy 2.2.0-2build1 amd64
  interactive processes viewer
3. Install the Package:
Once I confirmed the name was htop, I installed it. apt showed me what would be installed and asked for confirmation.

$ sudo apt install htop
Reading package lists... Done
Building dependency tree... Done
...
The following NEW packages will be installed:
  htop
0 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
Need to get 90.1 kB of archives.
After this operation, 238 kB of additional disk space will be used.
Do you want to continue? [Y/n] Y
4. Run the Program:
With the installation complete, I just had to type the command to run it. The interactive interface is a huge improvement!

htop
5. Remove the Package:
After exploring htop, I removed it using sudo apt remove.

$ sudo apt remove htop
Reading package lists... Done
Building dependency tree... Done
...
The following packages will be REMOVED:
  htop
0 upgraded, 0 newly installed, 1 to remove and 0 not upgraded.
After this operation, 238 kB disk space will be freed.
Do you want to continue? [Y/n] Y

6. Clean Up (Bonus):
I learned that sudo apt autoremove is a good command to run periodically to remove any dependencies that were installed for packages but are no longer needed.
