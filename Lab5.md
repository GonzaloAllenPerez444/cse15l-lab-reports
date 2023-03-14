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
ls -t

written_2/             FileHelpers.class        URLHandler.class     start.sh           wordcountdir.sh   TestDocSearch.java  DocSearchServer.java
DocSearchServer.class  Server.class             TestDocSearch.class  results2           find-results.txt  Server.java
Handler.class          ServerHttpHandler.class  test.sh              find-results2.txt  lib/              README.md

```
Ls -t lists the items in a directory based on modification time; one use case of this is checking if a script actually modified the files you wanted in the correct order. In example 5, I'm trying to get a chronological order of when I worked on each part of the lab. In example 6 below, I was testing a theory that using git clone doesn't clone the author's works in alphabetical order by their names; ls -t proved me wrong!

Example 6:
---

```
ls -t

Rybczynski/  Kauffman/  Fletcher/  Castro/  Berk/  Abernathy/

```




Option 4: ls -R

---
Source: chatGPT

ls -R is probably the most powerful on this list;it can go beyond the working directory and recursively print out every path on the entire filesystem; this is one of the most efficient ways to get an objective view of an entire filesystem. In example 7, I attempt to see a wide view of how many chapters each author has written, and ls -R presents that in a pretty accessible way.

Example 7:
---

```
ls -R

./Abernathy:
ch1.txt  ch14.txt  ch15.txt  ch2.txt  ch3.txt  ch6.txt  ch7.txt  ch8.txt  ch9.txt

./Berk:
ch1.txt  ch2.txt  CH4.txt  ch7.txt

./Castro:
chA.txt  chB.txt  chC.txt  chL.txt  chM.txt  chN.txt  chO.txt  chP.txt  chQ.txt  chR.txt  chV.txt  chW.txt  chY.txt  chZ.txt

./Fletcher:
ch1.txt  ch10.txt  ch2.txt  ch5.txt  ch6.txt  ch9.txt

./Kauffman:
ch1.txt  ch10.txt  ch3.txt  ch4.txt  ch5.txt  ch6.txt  ch7.txt  ch8.txt  ch9.txt

./Rybczynski:
ch1.txt  ch2.txt  ch3.txt

```

Here I want to see which countries are in the berlitz1 folder vs. the berlitz2 one.

Example 8:
---

```
ls -R

./berlitz1:
HandRHawaii.txt        HistoryEdinburgh.txt  HistoryLakeDistrict.txt  IntroIsrael.txt 
…

./berlitz2:
Algarve-History.txt      Bahamas-History.txt      Beijing-WhereToGo.txt   California-WhatToDo.txt      China-WhereToGo.txt       Cuba-WhereToGo.txt      PuertoRico-History.txt
Algarve-Intro.txt        Bahamas-Intro.txt        Berlin-History.txt 
 

```

