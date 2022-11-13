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

$< up_arrow_key >i

This will put you into insert mode at the curly brace at the line above the line listed in the task. To then place your cursor in the following position, type:

< right_arrow_key >< enter >< backspace >< space >< space >< space >< space >  

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-5-screenshot-3.png)

Now that our cursor is in the correct location, type the following line:

System.out.println(f.toString() + “ is a directory!”);

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-5-screenshot-4.png)

We're now finished with the task! Let's exit vim by first exiting insert mode with the escape key, and then inputting the :wq command to save and quit out of vim.

Part 2: Local and SCP edit vs SSH and Vim edit

When performing the above task via a local edit and a SCP command transfer, the entire task including running the test took about 1 minute and 30 seconds. Compare this to the edit using vim on the remote server (including testing and logging onto the remote terminal) the process was a shorter by 35 seconds, taking 55 seconds in total. 

There are pros and cons to using both methods. For the first method, VS code will alert you if you have made a mistake or not. This prevents any user error. On the other hand, this method does take longer to perform with the scp command, logging onto the remote terminal, and navigating to the file's directory in order to test it. The second method requires a lot less time, especially if you have a lot of practice with using vim. However, this method does allow for more user error to occur as Vim doesn't share the same functionality of poiting out Java errors like VS code does. If you were to miss a semicolon, Vim can't point that out to you in the moment and you instead have to interpret the error message when it comes time to run the tests.

I think generally I like the first method better. Despite the longer time, it ensures that I make little to no mistakes. Plus, at this moment in time I am more experienced with VS code as oppposed to Vim.

In a setting where I am allowed to make little to no errors, the first method is my perferred way to go. However, if I know the exact changes I need to make and the location of said changes, then I would for sure use Vim to save some time.


