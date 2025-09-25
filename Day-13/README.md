# 🐧 Day 13: Scripting with Logic

## Today's Objective
To make my scripts more "intelligent" by using if/else statements to perform actions based on specific conditions.

## Key Learnings
The if/else Structure: I learned the basic syntax for conditional logic in Bash:


if [ condition ]; then
  # code to run if condition is true
else
  # code to run if condition is false
fi
The test Command ([ ]): The square brackets [ ] are actually a command (an alias for test). They evaluate the condition inside them and return true or false. The spaces around the brackets are mandatory!

Common Conditions: I learned about some of the most useful test flags:

[ -f "$file" ]: True if the variable $file exists and is a regular file.

[ -d "$dir" ]: True if the variable $dir exists and is a directory.

[ -z "$var" ]: True if the variable $var is empty (a zero-length string).

Ending with fi: The if block is terminated with fi ("if" spelled backward), which is a unique quirk of Bash scripting.

## Concepts & Keywords Practiced

if
then
else
fi
[ ]  (the test command)
-f   (test for file)
-z   (test for empty string)
## Task Walkthrough: Creating checker.sh
The task was to build a script that checks if a file exists, demonstrating the use of if/else.

1. Write the Script:
I created a file named checker.sh and wrote the following code. I included a check to make sure the user provides an argument.

#!/bin/bash

# This script checks if a file, provided as an argument, exists.

# First, check if an argument was given at all.
if [ -z "$1" ]; then
  echo "Usage: $0 <filename>"
  exit 1 # Exit with an error code
fi

FILENAME=$1

# Now, check if the file exists.
if [ -f "$FILENAME" ]; then
  echo "Success: The file '$FILENAME' exists."
else
  echo "Error: The file '$FILENAME' was not found."
fi
2. Make the Script Executable:
As always, I made the script runnable with chmod.

$ chmod +x checker.sh
3. Test Case 1: The File Exists:
First, I created a dummy file and then ran the script with it.

$ touch test_file.txt
$ ./checker.sh test_file.txt
Success: The file 'test_file.txt' exists.
4. Test Case 2: The File Does Not Exist:
I ran the script with a name for a file that doesn't exist.

$ ./checker.sh non_existent_file.txt
Error: The file 'non_existent_file.txt' was not found.
5. Test Case 3: No Argument Provided:
My initial check for an empty argument worked as expected.

$ ./checker.sh
Usage: ./checker.sh <filename>
## Personal Reflections
This was a huge step forward. My scripts can now handle errors and different scenarios, which makes them much more robust and useful. The syntax for the test command (with the spaces and brackets) is a bit particular, but I can see it becoming second nature with practice. The ability to check for conditions before taking action is the foundation of real programming, and it's exciting to be able to do this in Bash.
