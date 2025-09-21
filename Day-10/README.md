### 🐧 Linux Journey Day 10: System Logs & The File System Hierarchy
## Today's Goal

## What I Learned
System Logs: I learned that Linux is constantly recording events, errors, and informational messages in log files. These are the first place to look when something goes wrong.

journalctl: This is the modern, powerful tool to query system logs in a structured way.

dmesg: This command shows kernel-related messages, which is super useful for debugging hardware issues.

tail -f: This is my new favorite command! It lets you watch a file in real-time and see new lines as they are added, which is perfect for monitoring logs.

File System Hierarchy (FHS): I learned that the directory structure isn't random; it follows a standard called the FHS. Understanding this "map" makes it so much easier to find things.

/etc: Holds all system-wide configuration files.

/var: Contains variable data, like logs, caches, and spools.

/bin: Contains essential user command binaries (programs).

/home: Where user personal directories live.

## Commands I Practiced
journalctl: To query the systemd journal for logs.

dmesg: To view kernel messages.

tail -f: To "follow" a file and watch its output live.

## My Experience
(This is your space to write! For example: The task today was a fantastic demonstration. I had one terminal running tail -f /var/log/syslog and in another, I ran sudo apt update. Seeing the network and package management events scroll by in real-time in the first terminal was an amazing "aha!" moment. It showed me exactly how the system records its actions. Reviewing the FHS finally made the directory structure click; it's not just a random collection of folders, but a logical, organized system.)
