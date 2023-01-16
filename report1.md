Foster Dang  
Published 1/11/2023  
Last Updated 1/11/2023  
CSE 15L
Content heavily lended from https://ucsd-cse15l-w23.github.io/week/week1/#week-1-lab-report

# Tutorial for Noobs<br><br>1. VSCode
So, the first order of business is downloading Visual Studio Code (VScode).<br>
<br>
Click this [link](https://code.visualstudio.com/download), bro.  
Choose the big blue button corresponding with the operating system you have  
![image](https://user-images.githubusercontent.com/96316038/211932916-f2c6f8c6-9ef5-4756-9723-cfbaf1da3f09.png)
<br>
Open the installer, the thing that you just downloaded, and just accept the agreement and leave all the options as they are and click install. 
<br><br>
Once you have it installed, open it. Congrats, you are now a VScoder. You should see something like this.
![image](https://user-images.githubusercontent.com/96316038/211933342-d87b49c9-85cc-405c-87d5-aaa08bec6479.png)
<br>
# 2. Remotely Connecting  
Now that you're in VScode, it's time to remotely connect to the server. This will let you connect to a remote computer and work on it. 
<br><br>
If you're on Windows, the first step is to install git, if you haven't before. Here's the link, knock yourself out:  
<br>[Git for Windows](https://gitforwindows.org/)  
<br>From here on out, I will describe the process from a Windows point of view, as that is the way that I did it.  
<br>
Open a terminal by clicking this thing, or pressing `Ctrl` + `Shift` + `` ` ``:  
![image](https://user-images.githubusercontent.com/96316038/212623744-32cd79e1-3a89-4006-aa2c-1e464178b678.png)

To use Git in this terminal follow this wonderful guide from a user on stackoverflow:
[Bash on Windows VScode](https://stackoverflow.com/a/50527994)  
<br>
Then, go here to find your account that you'll log in on. Your account name should look like `cs15lwi23zz@ieng6.ucsd.edu`:
[Link](https://sdacs.ucsd.edu/~icc/index.php)
If it's your first time using this account, you'll have to click reset password and even though it says "reset", you have to set your password there. You'll use this to log in.  
<br>
Back to VScode after you have all that info.  
<br>
Enter this into your Bash terminal on VScode:
`ssh [insert account name here]@ieng6.ucsd.edu`
<br>
You should see this:
```
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
```
Just type `yes` and enter. This is normal, but if it happens beyond the first time you login that might be an issue (ask for help).
Now you should enter the password that you set at the reset password page. Once you're on you should see something like this (note: if you just set your password, it might take a minute or two for the password to process and allow you to enter it so wait a bit):
```
# Now on remote server
Last login: Sun Jan  2 14:03:05 2022 from 107-217-10-235.lightspeed.sndgca.sbcglobal.net
quota: No filesystem specified.
Hello cs15lwi23zz, you are currently logged into ieng6-203.ucsd.edu

You are using 0% CPU on this system

Cluster Status 
Hostname     Time    #Users  Load  Averages  
ieng6-201   23:25:01   0  0.08,  0.17,  0.11
ieng6-202   23:25:01   1  0.09,  0.15,  0.11
ieng6-203   23:25:01   1  0.08,  0.15,  0.11

Sun Jan 02, 2022 11:28pm - Prepping cs15lwi23
```
Nice! Now you can mess around or whatever. Try these commands:
```
cd ~
cd
ls -lat
ls -a
ls <directory> where <directory> is /home/linux/ieng6/cs15lwi23/cs15lwi23abc, where the abc is one of the other group members’ username
cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/
cat /home/linux/ieng6/cs15lwi23/public/hello.txt
```
When you want to log off just press `Ctrl` + `D` or type and enter "exit".
When you log off the remote computer and you're back onto your local computer, try these commands to navigate and change your files with Bash:
`cd`, `ls`, `pwd`, `mkdir`, and `cp`
