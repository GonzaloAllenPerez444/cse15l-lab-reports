How To Log Into ieng6 - By Gonzalo Allen-Perez
==============================================
                                                               
                                                               
Make sure to read this slow and in order- it will 
save you some headaches, believe me. Check the _"potential problems you might run into"_ section at the bottom if you're having issues. 
                                                               
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


Select the option that “I know my password, and wish to change it” Enter your current password, and put the same password down below. You would think this might cause an error, but you’ll be ok. We only need to change the course-specific password, so if there's an option to not change your UCSD-wide password, you can select it. It might take upwards of 15 minutes to reset, so stay calm and don’t bully your computer in the meantime.


PART 2- OPENING UP OUR TERMINAL IN VSCODE
=========================================

Now that we have our credentials in order, we should download and open the best* code editor, VSCode. With VScode, we can open up a terminal that enables us to connect to the server.

To download VSCode, visit this link: https://code.visualstudio.com/download



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


Now that we’ve gotten our terminal in order,  paste “ssh” plus YOUR USERNAME FROM BEFORE + “@ieng6”  into the terminal. This makes a request to connect with the CSE basement server under your username. It should look something like this, with your specific username instead:

"___ssh cs15lwi23zz@ieng6.ucsd.edu___"


You should be met with this:

***
![login1](https://user-images.githubusercontent.com/106555298/212231030-87b896b6-82e5-4603-b898-192e5d0b0443.png)

***


Now put in your __RESET__ password and submit; You could be met with a little warning, feel free to just write “yes” and hit enter.
And Now as those Hackers in movies say, _"We’re In!”_ Congrats! Down below is what the bottom of your screen should look like:

***
![loggedin](https://user-images.githubusercontent.com/106555298/212231453-0d6d3a32-4b70-4aa1-8b65-6ef094cc8cce.png)
***

PART 4- RECONNAISSANCE
======================


Now that we’re here, let’s go exploring and take a look around. _Remember:_

- “ls” lists everything in the directory (use “ls -alt” to see hidden files!)
- “cd [name]” __changes directory__  to [name]. (use “ cd .. “ to go backwards and “cd ~” to go the base directory!)

Normal "ls" command:
-------
***
![image](https://user-images.githubusercontent.com/106555298/212234307-a8777d6e-9073-4d29-b789-fd91d1c8e8c2.png)

***


"ls" command with flags 0_0:
----------

***
![image](https://user-images.githubusercontent.com/106555298/212234135-a3545c53-9f27-4a0b-a5f9-34915287105f.png)

***




_The END_

***
***

Some Potential Problems You Might Run Into:
-------------------------------------------

- __Password doesn’t get accepted__:
 you need to make sure your ucsd password is reset, and make sure that your “ssh …..” command  is actually your username and not a wrong one

- __My UCSD account can’t be looked up__: 
Make sure that your username does not include the “@ucsd.edu” part at the end of it, and that your PID starts with A. Sometimes it can take a really long time to load.


