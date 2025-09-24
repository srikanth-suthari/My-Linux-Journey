### 🐧 Day 12: Intro to Shell Scripting

## Key Learnings
The Shebang (#!/bin/bash): This is the magic first line of a script. It's called a "shebang" and it tells the operating system which interpreter (in this case, /bin/bash) should be used to execute the commands in the file.

Variables: I learned how to declare and use variables to store data. The syntax is simple: NAME="value" to assign and $NAME to access the value.

Command-Line Arguments: This was a key concept. I can make my scripts interactive by reading input given on the command line when the script is run. These are called positional parameters:

$1 refers to the first argument.

$2 refers to the second argument, and so on.

$0 refers to the name of the script itself.

## Concepts & Commands Practiced

#!/bin/bash
$1
chmod +x
./script_name.sh
## Task Walkthrough: Creating welcome.sh
The task was to create a script that would greet a user by name, with the name provided as an argument.

1. Write the Script:
I created a file named welcome.sh and added the following code using nano.

## Sample Script

#!/bin/bash

# This script greets the user with the name provided as the first argument.

# Check if an argument was provided. If not, use "Guest".
if [ -z "$1" ]; then
  NAME="Guest"
else
  NAME=$1
fi

# Print the welcome message.
echo "Welcome, $NAME!"
Self-improvement: I added a small if statement to handle cases where no name is provided.

2. Make the Script Executable:
By default, the script file doesn't have execute permissions. I added it using chmod.

$ chmod +x welcome.sh
3. Run the Script with an Argument:
I ran the script from my current directory (./) and gave my name as the first argument.

$ ./welcome.sh Learner
Welcome, Learner!
4. Run it Without an Argument:
Thanks to the if statement, it still works gracefully.


$ ./welcome.sh
Welcome, Guest!
## Personal Reflections
Writing that first script and seeing it run felt like a huge accomplishment. It's a shift from being a user to being a creator. The concept of positional parameters ($1) is incredibly powerful and I can already see how it can be used to build flexible tools. Remembering to use chmod +x is a step I'll have to get used to, but it makes sense from a security perspective. I'm excited to build more complex scripts!
