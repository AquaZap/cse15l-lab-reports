Using Vim (Lab Report 5) - By Dean Bisco 

Part 1: Vim Task #2

The Task mentioned was to edit DocSearchServer.java to include a line before File[] paths = f.listFiles(); that prints out the toString of f and a message saying it's a directory.

Starting within the week6-skill-demo1 directory, you can type the following line in order to access the DocSearchServer file within vim:

vim < shift >d< tab >< enter >

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-5-screenshot-1.png)

Now to go to the line listed in the task, the following command can get you there:

/< shift >f< enter >

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-5-screenshot-2.png)

Next let's place our cursor right above this line in insert mode. First type:

$<up_arrow_key>i

This will put you into insert mode at the curly brace at the line above the line listed in the task. To then place your cursor in the following position, type:

<right_arrow_key>< enter >< backspace >< space >< space >< space >< space >

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-5-screenshot-3.png)

Now that our cursor is in the correct location, type the following line:

System.out.println(f.toString() + “ is a directory!”);

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-5-screenshot-4.png)

We're now finished with the task! Let's exit vim by first exiting insert mode with the escape key, and then inputting the :wq command to save and quit out of vim.

Part 2: Local and SCP edit vs SSH and Vim edit


