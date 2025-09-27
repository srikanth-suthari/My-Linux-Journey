## 🐧 Day 15: Final Project & Next Steps

## Today's Objective
To combine my scripting skills into a useful system report tool and to plan my future learning path.

## Journey Reflection
This 15-day challenge has been an incredible experience. I've gone from being intimidated by the terminal to feeling empowered by it. The biggest takeaway is the Linux philosophy of having small, simple tools that, when chained together, can perform incredibly complex tasks. Learning to think in terms of pipelines (|), scripts, and automation has fundamentally changed how I view interacting with a computer.

## Final Project: system_report.sh
The final task was to create a script that provides a quick overview of the system's current status. This project combines concepts like using system commands, echo for formatting, and the basic structure of a shell script.

1. The Script Code:
I created a file named system_report.sh with the following code to make the output clean and readable.


#!/bin/bash

# This script generates a quick report of the system's status.

echo "--- System Report Generated on $(date) ---"
echo "" # Blank line for spacing

echo ">> Uptime:"
uptime
echo ""

echo ">> Current User:"
whoami
echo ""

echo ">> Disk Space Usage (Root Partition):"
df -h /
echo ""

echo "--- End of Report ---"
2. Make it Executable:
As always, I made the script runnable.

$ chmod +x system_report.sh
3. Run the Report:
Executing the script now gives a clean, formatted report of the system's key stats.

Bash

$ ./system_report.sh
--- System Report Generated on Sat 27 Sep 2025 06:11:29 PM IST ---

>> Uptime:
 06:11:29 up 2 days,  4:18,  1 user,  load average: 0.10, 0.15, 0.12

>> Current User:
learner

>> Disk Space Usage (Root Partition):
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        50G   20G   30G  40% /

--- End of Report ---
## What's Next for Me?
This journey isn't the end; it's the foundation for what comes next. The skills I've learned are essential for so many modern tech fields. My next step will be to dive into [Your Choice Here: e.g., Docker].

Here are the paths I considered:

Docker & Containers: Use my Linux skills to build, run, and manage containerized applications.

Git & Version Control: A must-have skill for any developer, and it's used primarily from the command line.

Vim / Neovim: Go deeper into the command line by mastering a powerful terminal-based text editor.

Advanced Networking: Build on the basics by learning about firewalls, routing, and services like SSH and Nginx.

Thank you for following my journey!
