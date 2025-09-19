🐧 Day 8: User & Group Management

## Today's Objective
To learn how to create, manage, and delete users and groups on the system, a core task for any system administrator.

## Key Learnings
Users and Groups: I learned that a user is an account that can log in and own files, while a group is a collection of users. Granting permissions to a group is an efficient way to manage access for multiple people at once.

Key Files: The system keeps a record of all users in /etc/passwd and all groups in /etc/group. It's helpful to know these files exist, even if you don't edit them directly.

Important Flags: Two small flags made a huge difference:

useradd -m: The -m flag is crucial because it creates a home directory for the new user.

usermod -aG: The -aG flag appends a user to a supplementary group. Without -a (append), you would remove the user from all other groups they belong to!

## Commands Practiced

useradd
passwd
usermod
groupadd
userdel
id

## Task Walkthrough: Managing a Test User
Today's task was to perform the full lifecycle of creating and configuring a user and a group.

1. Create a New Group:
First, I created a group named testers that I could later assign users to.

$ sudo groupadd testers

2. Create a New User:
Next, I created a new user, making sure to include the -m flag to create their home directory.

$ sudo useradd -m tempuser

3. Set a Password for the User:
A new user account is locked until a password is set. The passwd command prompted me to enter and confirm a new password.

$ sudo passwd tempuser
New password:
Retype new password:
passwd: password updated successfully

4. Add the User to the Group:
I used the usermod command with the -aG flags to add tempuser to the testers group.

$ sudo usermod -aG testers tempuser

5. Verify the Changes:
The id command is perfect for checking a user's information. I could see that tempuser was now part of the testers group.

$ id tempuser
uid=1001(tempuser) gid=1001(tempuser) groups=1001(tempuser),1002(testers)

6. Delete the User:
Finally, I cleaned up by deleting the user. The -r flag is important here as it also removes the user's home directory.

$ sudo userdel -r tempuser
## Personal Reflections
This felt like I was putting on a system administrator's hat for the first time. The process is very logical and command-driven. Understanding the flags for commands like useradd and usermod is clearly very important to avoid making mistakes. The id command is a great tool for verifying that your changes worked as expected. This seems like a foundational skill for anyone wanting to manage a Linux server.
