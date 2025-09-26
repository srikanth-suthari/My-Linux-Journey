## 🐧 Day 14: Loops in Scripts

### Today's Objective
To use for loops to perform actions on multiple items, such as a list of files.

## Key Learnings
The for loop Structure: I learned the fundamental syntax for for loops in Bash, which allows me to iterate over a list of items and execute commands for each one.


for item in list_of_items; do
  # code to run, using "$item"
done
Iterating Over Files: The most powerful feature I discovered is using wildcards to generate the list of items. For example, for file in *.txt automatically creates a loop that runs once for every file ending in .txt in the current directory.

The Loop Variable: Inside the loop, the variable I define (item in the example above) holds the value of the current item from the list, allowing me to act on it. It's crucial to quote the variable (e.g., "$item") to handle filenames with spaces correctly.

## Concepts & Keywords Practiced

for
in
do
done
## Task Walkthrough: Creating header_reader.sh
The task was to build a script that finds all .txt files in its directory and prints the first line of each one.

1. Create Some Sample Files:
First, I needed some files for the script to work on. I created three simple text files.


$ echo "This is the first line of file one." > file1.txt
$ echo "Another file for testing." > file2.txt
$ echo "The header for the third file." > file3.txt
$ echo "This is a markdown file, should be ignored." > notes.md
2. Write the Script:
I created a file named header_reader.sh with the following code.

#!/bin/bash

# This script finds all .txt files in the current directory
# and prints the first line of each one.

echo "--- Reading First Lines of .txt Files ---"

for file in *.txt; do
  # Check if the file actually exists to avoid errors if no .txt files are found
  if [ -f "$file" ]; then
    echo ">> Reading from: $file"
    head -n 1 "$file"
    echo "" # Add a blank line for readability
  fi
done

echo "--- Script Finished ---"
3. Make the Script Executable:
I made the script runnable with chmod.

$ chmod +x header_reader.sh
4. Run the Script:
I executed the script. It correctly found and processed only the .txt files.

$ ./header_reader.sh
--- Reading First Lines of .txt Files ---
>> Reading from: file1.txt
This is the first line of file one.

>> Reading from: file2.txt
Another file for testing.

>> Reading from: file3.txt
The header for the third file.

--- Script Finished ---
## Personal Reflections
Loops are a complete game-changer. I can see now how you could write a script to resize hundreds of images, rename a batch of files, or run a test on multiple servers. Combining loops with the if statements I learned yesterday allows for incredibly powerful and flexible automation. This was one of the most exciting days of the journey so far, as it tied together many of the previous lessons into a very practical skill.
