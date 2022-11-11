Grep Command Line Options (Week 5 Lab Report) - By Dean Bisco

Grep: This command searches through a file/files for a string and prints the matching lines.

Options:

-n - this command option will result in the name of the file the string was found in, and the line number of where the string was found within the file to be printed before the actual line.

Examples:

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-4-screenshot-1.png)

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-4-screenshot-4.png)

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-4-screenshot-5.png)

This option is useful for pinpointing the exact location of the string, especially if you are looking for a very specific sequence of words. 

-c - this command option will result in each file's name within the directory to be printed out with a number next to it. This number corresponds to the number of times the searched string shows up.

Examples:

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-4-screenshot-2.png)

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-4-screenshot-6.png)

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-4-screenshot-7.png)

If you don't want to see the specific line(s) the string appears in and only want to see the number of times it appears within a given directory, then this command option is very useful.

-i - this command option will take the string and search for all occurences of the word, whether it be capitalized or not. Without this -i flag, the capitilization will matter.

Examples:

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-4-screenshot-3.png)

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-4-screenshot-8.png)

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-4-screenshot-9.png)

This option lessens the strict rules by which strings and the grep command abide by and may prevent calculation errors made by the user.


