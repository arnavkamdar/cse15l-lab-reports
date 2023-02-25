# Lab report 4 : CSE Labs Done Quick
## A step-by-step walkthrough of the week 7 in-lab competition
---
**Steps 1-3:** Make a fork of the [repo](https://github.com/ucsd-cse15l-w23/lab7) in your personal account and delete any other existing forks you may have, then start the timer. 

**Step 4: Log into ieng6.**
![image](https://media.discordapp.net/attachments/984886152156811315/1078838969606873258/image.png?width=1250&height=656)

_Keyboard sequence used:_ `<up><enter>`
- On my terminal, I conduct all my code on my ieng6 account. 
- Thus, the terminal's most recent command is `ssh cs15lwi23adi@ieng6.uscd.edu`, which I have set up to not require a password on my laptop. 
- Pressing up and enter runs this command, logging me into my ieng6 account. 

**Step 5: Clone your fork of the repository from your Github account.**

Using `<Ctrl+R>`: 
![image](https://cdn.discordapp.com/attachments/984886152156811315/1078840188429676554/image.png)

Output: 
![image](https://user-images.githubusercontent.com/122496384/221326322-bf5a818a-2251-4cf8-bf32-70e99e7195d9.png)

_Keyboard Sequence used:_ `<Ctrl + R> git clone <tab> <enter>`
- Since I have participated in this competition in the lab, all the important commands are saved in my ieng6 history. 
- Thus, I used `<Ctrl + R>` to access my search history, typed in `git clone` to find the first git clone command, used `<tab>` to print the full line on my terminal, and entered it to clone it from my github's personal ssh url. 

**Step 6: Run the tests, demonstrating that they fail.**
![image](https://cdn.discordapp.com/attachments/984886152156811315/1078853511011385344/image.png)

_Keyboard Sequence used:_ `cd lab7 <enter> <Ctrl + R> javac <tab> <enter> <Ctrl + R> java -cp <tab> <enter>`
- First, I used `cd lab7` to change the working directory to the cloned directory lab7, and then used `<Ctrl + R>` to open my search history, searched for `javac`, and pressed `<tab>` and `<enter>`. This used the command `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` and compiled all the java files in lab7. 
- Then, I used `<Ctrl + R>`, `java -cp`, `<tab>`, and `<enter>` in a similar fashion to run the java file `TestListExamples.java` using the command `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples`. 
- Had I used just `<Ctrl + R>` and `java`, pressing tab would autofill the javac command, which is why I had to specify `java -cp` so that the terminal knew it was a java command I wanted to search for. 


**Step 7: Edit the code file to fix the failing test.**

Using `nano`:
![image](https://media.discordapp.net/attachments/984886152156811315/1078843758797389925/image.png)

Editing the file:
![image](https://cdn.discordapp.com/attachments/984886152156811315/1078844998054858762/image.png)

_Keyboard Sequence used:_ `nano ListExamples.java <enter> <Ctrl + W> index1 += 1 <enter> <Ctrl + W> <enter> <Ctrl + W> <enter> <right> <right> <right> <right> <right> <delete> 2 <Ctrl + O> <enter> <Ctrl + X>`
- First, I used `nano ListExamples.java` and `<enter>` to open `ListExamples.java` for editing. 
- Using `<Ctrl + W>` allowed me to search for `index1 += 1` by pressing enter. Repeating `<Ctrl + W>` and `<enter>` twice more allowed me to reach the third instance of `index1 += 1`, which is the one I wanted to edit.
- The cursor was now before the line `index1`, so to change this to `index2`, I pressed `<right>` five times, and used `<delete>` and `2` to replace the 1 with a 2. 
- After this, I used `<Ctrl + O>` and `<enter>` to save the file, and `<Ctrl + X>` to exit the nano interface.

**Step 8: Run the tests, demonstrating that they now succeed.**
![image](https://cdn.discordapp.com/attachments/984886152156811315/1078853745896587354/image.png)

_Keyboard Sequence used:_ `<up><up><up><enter><up><up><up><enter>`
- The `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` command was 3 up in the search history, so I used the up arrow to access it. 
- The `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests.java` command was 3 up in the search history, so I used the up arrow to access it. 

**Step 9: Commit and push the resulting change to your Github account.**
![image](https://media.discordapp.net/attachments/984886152156811315/1078855354059849878/image.png)

_Keyboard Sequence used:_ `<Ctrl + R> git commit <tab> <enter>`
- Using `<Ctrl + R>` and typing `git commit` and using `<tab>` autofills the command `git commit -am "M" && git push`, a command that was in my terminal history.
- `git commit -am "M"` adds all changes and commits the changes with the commit message "M". 
- `&& git push` additionally pushes the commit to my github account, where the change on the file can be seen with the commit message "M". 

![image](https://cdn.discordapp.com/attachments/984886152156811315/1078856594013556806/image.png)
