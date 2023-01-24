# Lab 1 Report
## Brian Liu 4:00 PM Thursday

Welcome to CSE 15L! Here are some steps on logging into your remote course-specific account on ieng6.

**Step 1: Installing VSCode** 

Make sure you've installed VScode on your computer.

If you don't already have it, install it here: 
[VSCode Install](https://code.visualstudio.com/download)

Open up the text editor, you should see something like this:

![Image](enterVS.png)

**Step 2: Remotely Connecting**

If you're on a Windows device, follow these 2 steps before continuing: 
  1) Make sure you have Git installed on your computer.
  [Git Installation](https://gitforwindows.org/)

  2) Then, set your VSCode default terminal to use git bash.
  [Set VSCode terminal to Bash](https://stackoverflow.com/a/50527994)
  
Type in this in your terminal (replace "cs15lwi23zz" with your own course-specific account name)

```
$ ssh cs15lwi23zz@ieng6.ucsd.edu
```

You should get a message asking you if you're sure you want to connect to the server. Type in yes and then press enter.

Enter your associated password now and then press enter. Don't be surprised when the cursor doesn't move as you type the password, this is how it's designed.

Once you type in your password, you should be connected to your remote computer. 

Your screen should look something like this:

![Image](loggedin.png)

**Step 3: Trying Some Commands!**

Make sure everything works! Try out some terminal commands and explore the directories.

Like this:

![Image](practiceCommands.png)

In this screenshot, you can see some of the commands I tried out.

Changing the working directory to my personal directory (replace "cs15lwi23avx" with your own course-specific account name)
```
$ cd cs15lwi23avx
```

Viewing list of files/directories in my directory
```
$ ls
```

Viewing list of ALL files, including hidden files that begin with '.'
```
$ ls -a
```

Viewing list of ALL files, sorted by date (most recent on top)
```
$ ls -lat
```

Displaying text file contents
```
$ cat /home/linux/ieng6/cs15lwi23/public/hello.txt
```

**You did it!**

Playing around with the commands after connecting greatly helped my knowledge of terminal commands. Prior to trying these commands out, I had never heard of ls ~a or ls ~lat, and I honestly had no idea about hidden files starting with '.' It also provided further practice with basic commands like cd and ls, making sure I was fully comfortable with these fundamentals.


