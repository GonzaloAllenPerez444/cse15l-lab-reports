Step 1
===

Keys Pressed: (`<left click>` and `<right click>` together)

ssh cs15lwi23atd@ieng6.ucsd.edu 'rm -rf lab7/;git clone git@github.com:GonzaloAllenPerez444/lab7.git;cd lab7/;javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java;java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTest'

![image](https://user-images.githubusercontent.com/106555298/221093220-42e8c28b-48f9-445a-9904-b4fc66c63d5b.png)

Explanation
---

This is a whole number of commands all bunched together. We use single quotes to show that there’s multiple commands, then each subsequent command is followed by a semicolon. In order:
* First we `ssh` into ieng6. Since we downloaded our public ssh key onto the server, we don’t need to type in our username and password.
* Next we `rm` the lab7 directory if there’s already a copy of it.
* Clone a copy of the github repository
* `cd` into the directory and compile and run the JUNIT tests 

---

Step 2
===

Keys Pressed:  `<up>` `<up>` `<enter>`

![image](https://user-images.githubusercontent.com/106555298/221093733-10bdc17d-259e-464c-a88c-749b771bf565.png)

Explanation:
This lets us ssh us back into the server. The command was already second back in my history so I could just refer to the command from there.

---

Step 3
===

Keys Pressed:
`cd l <tab>`
`nano L <tab>.java`
`<down * 42> , <right * 12>, <backspace> 2`
`<Crtl + o> <enter> <crtl + x>`

![image](https://user-images.githubusercontent.com/106555298/221094097-cf3d80dc-878a-4a63-b7db-32e25a2bd3a4.png)

![image](https://user-images.githubusercontent.com/106555298/221094131-3ee42877-ea62-48d0-9c0c-4bf533d6e3da.png)

Explanation:here we open up ListExamples.java in the nano text terminal, then navigate to the bug and replace index1 with index2. I experimented with using the `sed` command so we wouldn’t have to open the editor manually,but I couldn’t get it working right.

---

Step 4
===

Keys Pressed: `<Ctrl + c> <Ctrl + v>`

![image](https://user-images.githubusercontent.com/106555298/221094929-af1d4999-dd5b-4924-b907-c8f296f52f7a.png)

Explanation: I copied the Junit compile and test commands I had saved.

---

Step 5
===

Keys Pressed:
`git add . `
`Git commit -m “done” `

![image](https://user-images.githubusercontent.com/106555298/221095034-a7f68ad7-25e0-476c-9ce7-3bbfb0eceadb.png)

Explanation: this stages all files to commit and commits ListExamples.java with the message “done”.

---

Step 6
===

Keys Pressed:
`Git push`

![image](https://user-images.githubusercontent.com/106555298/221095181-a281298f-b509-44fb-a3eb-86e3d7383db0.png)


Explanation: We already had an `ssh` key with github, so we could just push freely without having to provide credentials or specify remote.


