Day 2: Manipulating Files & Understanding Permissions 🚀
Today's Focus: Learning how to create, copy, move, and delete files and directories, and understanding the fundamental Linux security model of file permissions.

💡 What I Learned
Today's session moved from navigating the filesystem to actively manipulating it. I also took a deep dive into how Linux controls access to every file and directory.

File & Directory Manipulation Commands
I learned the essential commands for managing the lifecycle of files:

cp (copy): Used to copy files or directories. cp source_file destination_file. For directories, the -r (recursive) flag is needed: cp -r source_dir destination_dir.

mv (move/rename): This command has a dual purpose. It can move a file to a new directory (mv file.txt /new/dir/) or rename it in the same location (mv old_name.txt new_name.txt).

rm (remove): Used to permanently delete files. For directories, the -r (recursive) flag is required. I learned to use this command with caution, as there is no "recycle bin" on the command line!

cat, less, more: Different ways to view file contents. cat displays the entire file in the terminal, which is good for short files. less and more are "pagers" that let you view large files screen by screen.

head, tail: Used to view the first few (head) or last few (tail) lines of a file, which is very useful for checking log files.

Understanding File Permissions
This was a critical concept for understanding Linux security. Every file and directory has a set of permissions that control who can do what with it.

Reading Permissions with ls -l: The command ls -l shows a permission string like -rwxr-xr--.

The first character indicates the file type (- for a file, d for a directory).

The next nine characters are three sets of three:

User (Owner): Permissions for the user who owns the file (rwx).

Group: Permissions for the group that owns the file (r-x).

Others: Permissions for everyone else (r--).

Permission Types:

r (read): View the contents of a file or list the contents of a directory.

w (write): Modify a file or create/delete files within a directory.

x (execute): Run a file as a program or cd into a directory.

chmod (Change Mode): The command used to modify permissions. I learned two methods:

Symbolic: Using letters to add (+), remove (-), or set (=) permissions (e.g., chmod g+w notes.txt adds write permission for the group).

Octal (Numeric): Using numbers to represent permissions (4=read, 2=write, 1=execute). chmod 755 script.sh sets rwx for the owner and r-x for the group and others.

🛠️ Hands-On Lab
Created a directory named lab-day2 and navigated into it.

Used touch to create file1.txt and cp to create file2.txt as a copy.

Renamed file1.txt to main.txt using the mv command.

Created a subdirectory called archive and moved file2.txt into it.

Viewed the default permissions of main.txt with ls -l.

Used chmod u-w main.txt to remove write permissions for myself (the owner) and confirmed I could no longer edit it.

Created a simple script hello.sh and used chmod 744 hello.sh to make it executable for the owner, but read-only for everyone else.

✨ Key Takeaway
Linux provides precise and powerful tools for both managing files and securing them. While commands like cp and rm are the workhorses for organization, the permission system is the foundation of security and multi-user functionality. Understanding chmod is non-negotiable for ensuring that files are only accessible to the users and services that should have access to them.
