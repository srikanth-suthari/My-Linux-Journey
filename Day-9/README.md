🐧 Linux Journey Day 9: Process Management

## Today's Goal
My objective was to monitor running processes and learn how to stop them gracefully or forcefully using command-line tools.

## What I Learned
Process & PID: Every running application is a process, and each one is assigned a unique Process ID (PID) that the system uses to manage it.

htop: This is a fantastic, user-friendly, and interactive tool for viewing all running processes. It gives a real-time overview of system stats like CPU and memory usage and makes it easy to sort and manage processes.

ps: This is the classic, non-interactive way to get a snapshot of the system's processes. The ps aux command is a powerful combination to see every process running on the system.

kill and Signals: The kill command is more nuanced than its name suggests. It doesn't just destroy a process; it sends a signal. The default signal (SIGTERM or -15) asks the process to shut down gracefully. If a process is stuck, you can use kill -9 (SIGKILL) to force it to terminate immediately.

## Commands I Practiced
ps aux: A great command to get a detailed snapshot of all running processes.

htop: An interactive, real-time process viewer.

kill <PID>: To send a termination signal to a specific process.

killall <process-name>: To terminate all processes with a specific name.

## My Experience
(This is your space to write! For example: The task today was very practical. I opened the nano text editor and then used another terminal to hunt it down. Running ps aux | grep nano worked perfectly to find its PID. Using kill on that PID and seeing the editor window instantly disappear was a great demonstration of how much control you have from the command line. htop is definitely a tool I'll be using all the time; its visual layout is so much easier to understand at a glance than the wall of text from ps.)
