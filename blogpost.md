How To Log Into ieng6 - By Gonzalo Allen-Perez
==============================================
                                                               
                                                               
Make sure to read this slow and in order- it will 
save you some headaches, believe me.
                                                               
__What The Heck Are We Doing?__

In this lab we are connecting to a remote server in the CSE basement using the “ssh” command in the vscode terminal.

PART 1- Finding your Username and Changing your Password
========================================================
>This Part is SUPER important!

First, in order to log into the server, we need to reset our ucsd email for 15L. As it stands now, we won’t be able to sign in with our normal password. We can “change” our ucsd password, while keeping it the same as it was before, so don’t fret.  First, go here: 

_https://sdacs.ucsd.edu/~icc/index.php_

Log in with your ucsd email WITHOUT THE “@ucsd.edu” And your student PID


You should be met with a screen like this (Note that you might see a yellow banner telling you to change your password, this is fine :) ). The red circled box contains your username to log into the server. Save it somewhere you can access it easily.


***

![UCSD LOGIN](https://user-images.githubusercontent.com/106555298/212228786-e06791dc-b05f-40e1-a8b3-023b5ea564ca.png)

***


Now, we can “change” (not really changing!) our password from here. Go to the linked Change your password site (either in the yellow banner or on the page)


Select the option that “I know my password, and wish to change it” Enter your current password, and put the same password down below. You would think this might cause an error, but you’ll be ok. It might take upwards of 15 minutes to reset, so stay calm and don’t bully your computer in the meantime.


PART 2- OPENING UP OUR TERMINAL IN VSCODE
=========================================

Now that we have our credentials in order, we should open (I’m assuming you have used vscode in the past for CSE 11 or 8B, but if not just go to the Vscode website, download the corresponding one for your operating system, and run the file once it finishes downloading.)

***
![DownloadScreen](https://user-images.githubusercontent.com/106555298/212229471-702cceef-cc8b-4f1b-8d8a-b257fa8c7992.png)
***



Open VSCode up, and you should be met with this screen. 

***
![Vscode main screen](https://user-images.githubusercontent.com/106555298/212229639-1e7acb84-270d-40f9-be41-0ddabafecf6d.jpg)

***

Go to the taskbar at the top of the screen, and select -> terminal -> New Terminal. Something like this will pop up:

***
![TerminalPic](https://user-images.githubusercontent.com/106555298/212229863-e16379d8-8b3e-44b0-aff1-2cd91e2dc1f1.png)
***

Don’t be alarmed if your terminal looks slightly different from mine; if you are on a windows or mac, you might be using “powershell” or the mac terminal, whereas the above image is using the “bash” command line. You don’t have to change it for this tutorial, but I would recommend it since it makes life on the command line easier in pretty much every way.



To change from powershell to bash (i can’t screenshot this unfortunately :( ), _go to the top bar to view -> command palette._ Inside the command palette, type _“select default profile”_ and click what pops up. Select _“git bash”._ Now open up a new terminal.


***
![changeBash](https://user-images.githubusercontent.com/106555298/212230413-c3f2b869-2679-4a74-84a3-ab83265a9d00.png)
***


You can see this on the right of the terminal. Click on the down arrow and from there you can select to switch from your current terminal to bash, or open a new bash terminal.


 
PART 3- LOGGING INTO THE SERVER
===============================




