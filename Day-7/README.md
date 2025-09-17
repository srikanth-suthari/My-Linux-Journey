🐧 Linux Journey Day 7: Text Manipulation & Archiving

## Today's Goal
My objective was to perform basic text substitution, process column-based data, and learn how to bundle and compress files into a single archive.

## What I Learned
sed (Stream Editor): This is the command-line equivalent of "find and replace." It's incredibly fast for making programmatic changes to text files without ever having to open them in an editor.

awk: This is a powerful tool for processing text that's structured in columns. I learned that it's perfect for slicing up the output of commands like ls -l to extract just the pieces of information you need.

tar (Tape Archive): I learned that tar by itself is an archiver, not a compressor. It bundles many files and directories into a single .tar file for easy transport. To actually compress the file, you combine tar with a tool like gzip, which is as simple as adding the z flag to the command.

## Commands I Practiced
sed 's/old/new/': The basic substitution command for sed.

awk '{print $9}': The basic awk command to print the ninth column of text.

tar -czvf: Create a g**z**ipped archive, be verbose, and use the specified file name.

tar -xzvf: Extract a g**z**ipped archive, be verbose, from the specified file name.

