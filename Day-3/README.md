# 🐧 Linux Journey Day 3: Permissions & Ownership

Day three was a deep dive into what makes Linux so secure and robust: its **permission system**. I learned how the OS controls who can read, write, and execute files, and how to perform administrative actions safely.

---

### ## Today's Goal
My objective was to **understand and modify file permissions and ownership**, and to learn how to use `sudo` to run commands with elevated privileges.

---

### ## What I Learned
- **Decoding Permissions:** The `ls -l` command is incredibly informative. I learned to read the permission string (like `-rwxr-xr--`) and understand what it means for the **user** (owner), the **group**, and **others**.
- **Changing Permissions:** `chmod` (**ch**ange **mod**e) is the tool to alter these permissions. I practiced with symbolic mode (`u+x` to add execute permission for the user) which feels very intuitive.
- **Changing Ownership:** `chown` (**ch**ange **own**er) is straightforward; it lets you change which user and group own a file.
- **Superuser Power:** `sudo` (**S**uper **U**ser **Do**) is the gateway to administrative power. It's the proper way to run commands that require root-level access without logging in as the root user directly, which is much safer.



---

### ## Commands I Practiced
- **`ls -l`**: The "long" list format, which displays detailed file information including permissions and ownership.
- **`chmod`**: The command to change file permissions. I used `chmod +x` to make a script executable.
- **`chown`**: The command to change a file's owner and group.
- **`sudo`**: The command to execute a single command with root privileges.

---

### ## My Experience
*(This is your space to write! For example: The "aha!" moment for me was creating a shell script and seeing the "Permission denied" error, then instantly fixing it with `chmod +x`. It really clicked why permissions are so important. Using `sudo` to create a file owned by root and then changing its ownership back to myself was a great practical exercise that showed the separation between a normal user and an administrator.)*

---

**Onward to Day 4:** It's time to learn how to manage software with package managers.

#Linux #15DayChallenge #Security #SysAdmin #CommandLine
