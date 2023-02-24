Step 1
----

Keys Pressed: (`left click` and `right click` together)

ssh cs15lwi23atd@ieng6.ucsd.edu 'rm -rf lab7/;git clone git@github.com:GonzaloAllenPerez444/lab7.git;cd lab7/;javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java;java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTest'

![image](https://user-images.githubusercontent.com/106555298/221093220-42e8c28b-48f9-445a-9904-b4fc66c63d5b.png)

Explanation
---

This is a whole number of commands all bunched together. We use single quotes to show that there’s multiple commands, then each subsequent command is followed by a semicolon. In order:
...First we ssh into ieng6. Since we downloaded our public ssh key onto the server, we don’t need to type in our username and password.
...Next we rm the lab7 directory if there’s already a copy of it.
...Clone a copy of the github repository
...Cd into the directory and compile and run the JUNIT tests 
