# Lab Report 5
---
For this lab report, I chose to redo Lab Report 4 with a (in my opinion) far more efficient method of executing a large number of functions: using a bash script. In the following report, I will explain how each step can be converted into part of a bash script. 

**Steps 1-4:**

These steps cannot be made any simpler by the usage of a bash script, as they require manual work on the part of the user. Step 4 requires the user to log in to their remote account, and while this can be done on a bash script (for example, simply typing `ssh cs15lwi23adi@ieng6.ucsd.edu`), the bash script failed to execute further for me inside the remote account. Thus, the bash script should be made in the home directory of your remote account. 

Create a bash script by using the command `nano labreport4quick.sh` in your home directory. This should open an interface as such: 

![image](https://cdn.discordapp.com/attachments/984886152156811315/1083247206791921754/image.png)

Now, we need to make the entire bash script in this file, so don't close this until done writing the entire script. 

**Step 5: Clone your fork of the repository from your Github account.**

Since the command I used here was simply `git clone git@github.com:arnavkamdar/lab7.git`, I just typed this into the bash script. This uses the ssh key for my fork of the lab7 repository. 

**Step 6: Run the tests, demonstrating that they fail.**

First, change the working directory to lab7. For this, type into your bash script 
`cd lab7`

To run the tests, I simply used the commands 

`javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`

`java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`

All one has to do is to copy these lines into the bash script. 

**Step 7: Edit the code file to fix the failing test.**

This was a very tricky step to resolve by writing a bash script. In my fourth lab report, I used the `nano` interface to edit my file. However, here, I want the computer to automate all the editing, and not require any further input from me. 
Research led me to [this website](https://www.gnu.org/software/sed/manual/sed.html), which helped me understand how to do this. I used the command `sed`, which edits specific words/lines in a file without requiring any further user input. The command I typed into the bash script was 
`sed -i '43s/index1/index2/' ListExamples.java`
- Here, the `sed` command, as mentioned, is the basis for editing a file. 
- The `-i` command added on allows the file to be edited without output redirection, as the standard for the `sed` command is to redirect the changes into a new output file. However, we want to simply edit `ListExamples.java` here and not create a new file. 
- Now, the `43s/index1/index2/` changes the second argument passed, `index1`, to the third argument passed, `index2`, as this is the change we need to make to fix the bug. 
- `43` represents the line number at which this change would be made, as otherwise, this command would alter every single instance of `index1` in the file, which is not the behavior we want.

**Step 8: Run the tests, demonstrating that they now succeed.**

As above, simply copy the lines 

`javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`

`java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`

into the bash script, and this part of the code will run the tests. 

**Step 9: Commit and push the resulting change to your Github account.**

In my lab report 4, I used the command `git commit -am "M" && git push` to commit the change with the commit message "M", and push it to the origin all in one line. Here, I reused this line, pasting it into my bash script. 

To finally close and save your bash script, use `<Ctrl + O>` to save, and `<Ctrl + X>` to exit.

**Final Bash Script:**

This is what my final bash script looked like: 

`git clone git@github.com:arnavkamdar/lab7.git`
`cd lab7`
`javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`
`java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`
`sed -i '43s/index1/index2/' ListExamples.java`
`javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`
`java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`
`git commit -am "M" && git push`


Upon running it in my main working directory on my remote account, this is what the output looked like: 
![image](https://media.discordapp.net/attachments/984886152156811315/1083250152766181468/image.png?width=630&height=655)

As seen, the repository was cloned, the tests run (and failed), the file edited, the tests run again (and succeeded), and the commit made and pushed.

Going to my forked repository on github, the changes did indeed show up: 
![image](https://cdn.discordapp.com/attachments/984886152156811315/1083250436842205244/image.png)
![image](https://cdn.discordapp.com/attachments/984886152156811315/1083250727822045244/image.png)

Using a bash script allowed me to run this entire project in just one line, and also led me to learn new commands in linux! 
