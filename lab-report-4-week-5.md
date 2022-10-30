Grep/Find/Less Command Line Options (Week 5 Lab Report) - By Dean Bisco

Grep: This command searches through a file/files for a string and prints the matching lines.

Options:

-n - this command option will result in the name of the file the string was found in, and the line number of where the string was found within the file to be printed before the actual line.

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-4-screenshot-1.png)

This option is useful for pinpointing the exact location of the string, especially if you are looking for a very specific sequence of words.

-c - this command option will result in each file's name within the directory to be printed out with a number next to it. This number corresponds to the number of times the searched string shows up.

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-4-screenshot-2.png)

If you don't want to see the specific line(s) the string appears in and only want to see the number of times it appears within a given directory, then this command option is very useful.

-i - this command option will take the string and search for all occurences of the word, whether it be capitalized or not. Without this -i flag, the capitilization will matter.

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-4-screenshot-3.png)

This option lessens the strict rules by which strings and the grep command abide by and may prevent calculation errors made by the user.


Find: This command searches through a path and returns all the files are contained within that directory and any other subdirectories.

Options:

-type - this option will take in an argument and look for that specific type within the given path. I have brought two examples of this and I think they serve different functions despite being a part of the same option:

-type d - searches for only directories

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-4-screenshot-4.png)

-type f - searches for only files

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-4-screenshot-5.png)

The first option can help the user look for a specific directory or subdirectory to cd to, while the second option can help the user look for a specific file to perform other commands on like grep or less.

-depth - this command has a similar purpose to -type f, where it will prioritize the contents of each directory before the directory itself

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-4-screenshot-6.png)

The directories are normally prioritized, so if there happen to be a lot of them, then they will end up burrying the actual files underneath them. This is another good way of looking at just the files within a given path.


Less: This command, given a path or file, will allow the user to scroll through the file in the terminal directly, or scroll through a list of files within the terminal. 

Options: *Note that all of these screenshots were taken after inputting the less command. This is because while scrolling through a file, you can input any of the following commands by typing '-' and then one of the listed characters.

-S - this command will separate all lines that are squeezed together, making it so that there is always a gap in between lines. Calling this command again will restore the printed file back to normal.

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-4-screenshot-7.png)

This can help the user clearly read a file since all of the lines are no longer as close together as they were before.

-N - this command will cause a line number to appear before each line.

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-4-screenshot-8.png) 

This can help the user find a specific line. For example, if they used the grep -n command on this file to find a specific word in a specific line, they can then use this command in order to find that line and that word.

-e - this command will make it so that when you reach the end of the file, it will quit out of the less command immediately.

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-4-screenshot-9.png)

Say if you're quickly scrolling through a long file in order to get the basic gist of the file. You may loop back to the beginning without noticing, so this command will help prevent that.