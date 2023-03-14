Command: ls
========

Option 1: ls -a
---------
Source: chatGPT prompt: "show me some cool options for the ls command"

Example 1:
-----

```
ls -a

./     DocSearchServer.class  find-results.txt   lib/       Server.class             start.sh             TestDocSearch.java  written_2/
../    DocSearchServer.java   find-results2.txt  README.md  Server.java              test.sh              URLHandler.class
.git/  FileHelpers.class      Handler.class      results2   ServerHttpHandler.class  TestDocSearch.class  wordcountdir.sh


```

 This flag lets you discover directories that are normally hidden; it’s really useful to see the underlying structures behind technologies like traversal and git. In the first example, I needed to check if I had initialized a git repository in my working directory, without ever touching git itself. Below, I tried to make a super secret file `.a.txt` to see if I could access it again. 

Exmple 2:
----

```
ls -a

O: ./  ../  .a.txt  non-fiction/  travel_guides/

```



Option 2: ls -l
---
Source: ls man pages

Example 3:
---
```
ls -l

total 0
drwxr-xr-x 1 gonza 197609 0 Feb  2 14:10 non-fiction/
drwxr-xr-x 1 gonza 197609 0 Feb  2 14:10 travel_guides/

```

the -l flag displays all of the files in long format, which also reveals info like the file permissions, metadata, and more besides just the name. This can come in handy whenever you’re doing custom actions on files like chmod. 


Example 4:
----

```
ls -l

-rw-r--r-- 1 gonza 197609 175513 Feb  2 14:10 WhereToIndia.txt
-rw-r--r-- 1 gonza 197609  85665 Feb  2 14:10 WhereToIsrael.txt
-rw-r--r-- 1 gonza 197609  90205 Feb  2 14:10 WhereToIstanbul.txt
-rw-r--r-- 1 gonza 197609 298768 Feb  2 14:10 WhereToItaly.txt
…

```

Here I want to find the largest file in the berlitz1 directory, so I quickly look over the results from ls -l to see that “WhatToDoItaly” has the largest size.

Option 3: ls -t
---
Source: ChatGPT!
Prompt: What are some more interesting ways to alter an ls command?

Example 5:
----
```
grep -i -v "a" China-History.txt

The Chinese Empire
Under Mongol Rule
Unity Eludes the Chinese
Imposing the New Order
```
The flag -v actually inverts the search, which can be equally powerful itself.
If I was trying to build a novel without the letter A (which is apparently a real things authors like to do like in this cool book [Gadsby](https://www.abebooks.com/books/gadsby-lipogram/)),
 I could look up inspiration from a file in a directory like this, which shows me each line in a file without the letter a.

Example 6:
---

```
grep -r -v -l  "Fuck"

O:
OUP/Abernathy/ch1.txt
OUP/Abernathy/ch14.txt
OUP/Abernathy/ch15.txt
OUP/Abernathy/ch2.txt
OUP/Abernathy/ch3.txt
OUP/Abernathy/ch6.txt
OUP/Abernathy/ch7.txt
OUP/Abernathy/ch8.txt
OUP/Abernathy/ch9.txt
OUP/Berk/ch1.txt
OUP/Berk/ch2.txt
OUP/Berk/CH4.txt
OUP/Berk/ch7.txt
OUP/Castro/chA.txt
OUP/Castro/chB.txt
OUP/Castro/chC.txt
OUP/Castro/chL.txt
OUP/Castro/chM.txt
OUP/Castro/chN.txt
OUP/Castro/chO.txt
OUP/Castro/chP.txt
OUP/Castro/chQ.txt
OUP/Castro/chR.txt
OUP/Castro/chV.txt
OUP/Castro/chW.txt
OUP/Castro/chY.txt
OUP/Castro/chZ.txt
OUP/Fletcher/ch1.txt
OUP/Fletcher/ch10.txt
OUP/Fletcher/ch2.txt
OUP/Fletcher/ch5.txt
OUP/Fletcher/ch6.txt
OUP/Fletcher/ch9.txt
OUP/Kauffman/ch1.txt
OUP/Kauffman/ch10.txt
OUP/Kauffman/ch3.txt
OUP/Kauffman/ch4.txt
OUP/Kauffman/ch5.txt
OUP/Kauffman/ch6.txt
OUP/Kauffman/ch7.txt
OUP/Kauffman/ch8.txt
OUP/Kauffman/ch9.txt
OUP/Rybczynski/ch1.txt
OUP/Rybczynski/ch2.txt
OUP/Rybczynski/ch3.txt
```

If we needed to censor all of our Non-fiction works by returning all chapters without the f-word in them, it would look something like the above; -v inverst the search for everything without the f-word in it. 


Option 4: -r
---
Source: man grep

Example 7:
---

```
grep -r "Hamburger" 
travel_guides/berlitz2/Berlin-WhereToGo.txt:Hamburger Bahnhof Museum
```

The -r flag is absolutely powerful as it lets you recursively search every file in a directory for a word and not just a single file. Here we power through every line in every file in the entire written_2 to find our sacred word "Hamburger", returning a single beautiful file.

Example 8:
---

```
Grep -r  -l “Drama”

travel_guides/berlitz1/WhatToGreek.txt
travel_guides/berlitz1/WhatToMadeira.txt
travel_guides/berlitz1/WhatToMalaysia.txt
travel_guides/berlitz1/WhereToFrance.txt
travel_guides/berlitz1/WhereToIndia.txt
travel_guides/berlitz2/Bali-WhatToDo.txt
travel_guides/berlitz2/Boston-WhereToGo.txt
travel_guides/berlitz2/Poland-WhatToDo.txt

```

If you’re a person who can’t get enough gossip and wants to keep up date with all of the ancient drama, this command is for you. It returns every file in the entire directory in which the word "drama" is inside. 

