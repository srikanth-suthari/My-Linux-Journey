## Today's Objective I/O Redirection & Pipes
To master controlling command input and output by redirecting to files and chaining commands together with pipes.

## Key Learnings
Standard Streams: I learned that every command operates with three standard streams: stdin (input), stdout (normal output), and stderr (error messages). By default, they are all connected to the terminal.

Redirection (> and >>): These operators let me change the destination of stdout.

> Redirects output to a file. If the file exists, it gets completely overwritten.

>> Appends output to a file. If the file exists, the new output is added to the end.

Pipes (|): The pipe is one of the most powerful concepts I've encountered. It takes the stdout of the command on its left and uses it as the stdin for the command on its right. It's like creating a "pipeline" where data flows from one tool to the next, getting processed at each step.

## Commands & Operators Practiced
Bash

>   (redirect and overwrite)
>>  (redirect and append)
|   (pipe)
## Task Walkthrough: Redirecting and Piping
Today's tasks involved capturing command output and creating a simple command pipeline.

1. Redirecting Output to a File:
I wanted to save a detailed listing of my home directory. The > operator was perfect for this.

Bash

# This command runs, but shows no output on the screen
$ ls -la ~ > home_listing.txt

# To verify, I used `cat` to view the new file's contents
$ cat home_listing.txt
total 60
drwxr-x--- 1 user user 4096 Sep 14 20:15 .
drwxr-xr-x 1 root root 4096 Sep 11 18:30 ..
-rw------- 1 user user 3328 Sep 14 19:55 .bash_history
... (and so on)
2. Using a Pipe to Filter Data:
I wanted to find all the standard network services related to http. Chaining cat and grep together with a pipe made this incredibly easy. cat dumped the file content, and grep filtered it.

Bash

$ cat /etc/services | grep http
http            80/tcp          www             # WorldWideWeb HTTP
https           443/tcp                         # http protocol over TLS/SSL
http-mgmt       280/tcp                         # http-mgmt
... (and other results)
This one-liner is so much more efficient than saving the file and then opening it to search manually.

## Personal Reflections
Pipes feel like a superpower. The idea that you can combine small, simple tools (cat, grep, ls, wc, etc.) to perform complex tasks is amazing. It really highlights the core philosophy of Linux: have many small programs that do one thing well, and then give the user the power to connect them. I/O redirection is also incredibly useful; I can already see myself using it to save logs and command outputs for review later.
