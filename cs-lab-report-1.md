# **Remote Access to your Course Account** 

## Step 1: Installing VS Code
* To install Visual Studio Code, visit the [VS Code website](https://code.visualstudio.com/). 
* Based on the OS your computer uses, download a version of VS code for you to use. 
* Once installed, your VS code should look like this: 
![Image](https://media.discordapp.net/attachments/794151037766336524/1063637840656879756/image.png?width=1246&height=664)

## Step 2: Remotely Connecting
* The first step in remotely connecting is to open up a terminal in your VS code. To do this, click on `Terminal --> New Terminal` in the menu bar. 
* To remotely connect to your account, type `ssh`, followed by a space, followed by your course-specific email account. This will have the syntax `username@ieng6.ucsd.edu`. The command line I used was 
`ssh cs15lwi23adi@ieng6.ucsd.edu` 
* Once you type this in and press enter, the following prompt should show up. 
`Password:`
* Type in your password (the characters will not show up on the command) and press enter when you are complete. This should remotely connect you to your account. If you see a message such as `Are you sure you want to continue connecting (yes/no/]fingerprint])?`, type in `yes` and proceed. 
* Your terminal should look like this: 
![Image](https://media.discordapp.net/attachments/794151037766336524/1063638163907690657/image.png?width=1440&height=460)

## Step 3: Trying Some Commands 
* To complete your set-up, you should now attempt to run some commands on your terminal to make sure everything is working. Start by typing `cd ~` into the terminal, which will switch the current directory to your home directory. 
* Follow this by using `ls` to view the list of files in your current directory. 
* Further, you can use the `mkdir hello` command to add a directory titled 'hello' into your current directory. Using `ls` again will then display this directory name as well. 
* If you wish to try more commands, attempt the following: 

  `cd`

  `ls -lat`

  `ls -a`

* Running all these commands may show results like this:
![Image](https://cdn.discordapp.com/attachments/794151037766336524/1063638580687273984/image.png)


* To log out of your remote connection, press 'Ctrl + D'. 

Congratulations! You have finished setting up remote access to your course account!
