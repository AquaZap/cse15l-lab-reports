How to Log Into YOUR Personal CSE 15L Account!

Step 1: Install Visual Studio Code (AKA VSCode)

 Follow this [Link](https://code.visualstudio.com/) in order to install the program

Once in VSCode, you will see the word Terminal. Click on that and open a new terminal.


Step 2: Remotely Connect to your CSE15L Account

Before we start connecting, if you're on windows install OpenSSH using this [Link.](https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse?tabs=gui) 

*Note that you may this installed so check by going to Settings -> Apps -> Optional Features then searching for OpenSSH in the search bar.

Now that you have OpenSSH installed, go into the new VSCode terminal you opened and type in the following command:

The "zz" is most likely a different pair of letters for you so make sure you look up what it is [here.](https://sdacs.ucsd.edu/~icc/index.php)

Whenever you're prompted with (yes/no/[fingerprint]) type in yes in order to move on from this prompt. After the first instance of this prompt, it will ask you for your password (You can reset it at the link above). You'll encounter the yes/no prompt once again, and once you type 'yes' you'll be connected to a computer in the CSE basement!

Now that you're remotely connected, let's try out some commands!

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-2-screenshot-2.png)

Above is a list of commands you can try within this terminal. Try them out! Once you're done, hit ctrl + D or type exit into the terminal in order to log out.

Now let's try moving files with the command SCP!

Let's try setting SSH Key!

Now, let's optimize our remote connection!