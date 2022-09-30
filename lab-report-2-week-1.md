How to Log Into YOUR Personal CSE 15L Account!

Step 1: Install Visual Studio Code (AKA VSCode)

 Follow this [Link](https://code.visualstudio.com/) in order to install the program

Once in VSCode, you will see the word Terminal. Click on that and open a new terminal.


Step 2: Remotely Connect to your CSE15L Account

Before we start connecting, if you're on windows install OpenSSH using this [Link.](https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse?tabs=gui) 

*Note that you may this installed so check by going to Settings -> Apps -> Optional Features then searching for OpenSSH in the search bar.

Now that you have OpenSSH installed, go into the new VSCode terminal you opened and type in the following command:

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-2-screenshot-1.png)

The "zz" is most likely a different pair of letters for you so make sure you look up what it is [here.](https://sdacs.ucsd.edu/~icc/index.php)

Whenever you're prompted with (yes/no/[fingerprint]) type in yes in order to move on from this prompt. After the first instance of this prompt, it will ask you for your password (You can reset it at the link above). You'll encounter the yes/no prompt once again, and once you type 'yes' you'll be connected to a computer in the CSE basement!


Now that you're remotely connected, let's try out some commands!

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-2-screenshot-2.png)

Above is a list of commands you can try within this terminal. Try them out! Once you're done, hit ctrl + D or type exit into the terminal in order to log out.


Now let's try moving files with the command SCP!

First, create a new java file called WhereAmI.java and use the following code within it:

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-2-screenshot-3.png)

Compile and run this program within your computer's terminal to confirm it works. Now use the following scp command

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-2-screenshot-4.png)

You'll be prompted to enter in your password. Once you do, the WhereAmI program should be copied into the remote terminal. Test this by entering it with the ssh command then compiling and running the WhereAmI.java file. Before moving onto the next step, logout of the terminal.


Let's try setting SSH Key!

You're probably wondering what this means? Basically, we're making it so that using ssh and scp commands don't require a password entry anymore. To do this, first type in this command:

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-2-screenshot-5.png)

This will cause a rsa key pair to start generating. When asked which file to save the key to, just hit enter to save it to the default path which should be /Users/(your username)/.ssh/id_rsa

This creates two new files on your own system, the private key in a file called id_rsa, and a public key in a file called id_rsa.pub stored in the .ssh directory of your computer. 

Next we need to copy the public key into the .ssh directory of your user account on the remote server. Do the following:

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-2-screenshot-6.png)

Once you logout of the terminal of your personal account's server, use the scp command on the following line:

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-2-screenshot-7.png)

(Note that "joe" should be replaced with your username)

Once you do this, congratulations! You can now use ssh or scp commands to your personal account's server without entering yoor account's password.


Now, let's optimize how we remotely run!

Logging onto your remote server every time you want to run a command on it can be a bit cumbersome at times. To bypass this, think of the command you want to run on your remote server. Once you do, put that command in quotes after the ssh call to your remote server account. It should look something like this:

![](https://aquazap.github.io/cse15l-lab-reports/lab-report-2-screenshot-8.png)

Also note that if you want to run multiple commands in succession, you can use semicolons in order to separate them. If you want to both compile then run the WhereAmI program type "javac WhereAmI.java; java WhereAmI".

Well Done! You now know how to run commands in your personal CSE 15L account's server, and have optimized the process for future endeavors!


