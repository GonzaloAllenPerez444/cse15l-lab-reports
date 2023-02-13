Command: Grep
========

Option 1: grep -l
---------

Example 1:
-----

```
grep -l "Italy" *.txt [berlitz1 directory]

HistoryFrance.txt
HistoryGreek.txt
HistoryIstanbul.txt
HistoryItaly.txt
HistoryMadeira.txt
HistoryMallorca.txt
IntroItaly.txt
IntroLasVegas.txt
WhatToItaly.txt
WhereToEgypt.txt
WhereToFrance.txt
WhereToFWI.txt
WhereToGreek.txt
WhereToIstanbul.txt
WhereToItaly.txt
WhereToMadrid.txt

```

-l is really useful because it just prints out the file names that contain the word, so it enables you to search a lot of files really efficiently. in the example above, I printed every file that had the word "Italy" in it, which could've taken more than a few minutes to test every file individually. 

Exmple 2:
----

```
grep -l "Spain" *.txt

Algarve-History.txt
Algarve-Intro.txt
Algarve-WhereToGo.txt
Amsterdam-History.txt
Bahamas-History.txt
Bahamas-WhereToGo.txt
Barcelona-History.txt
Barcelona-WhatToDo.txt
Barcelona-WhereToGo.txt
Beijing-WhereToGo.txt
Bermuda-history.txt
CanaryIslands-History.txt
CanaryIslands-WhatToDo.txt
CanaryIslands-WhereToGo.txt
Cancun-History.txt
CostaBlanca-History.txt
CostaBlanca-WhatToDo.txt
Costa-History.txt
Costa-WhatToDo.txt
Costa-WhereToGo.txt
CstaBlanca-WhereToGo.txt
Cuba-History.txt
Cuba-WhereToGo.txt
NewOrleans-History.txt
Paris-WhereToGo.txt
Portugal-History.txt
Portugal-WhatToDo.txt
Portugal-WhereToGo.txt
PuertoRico-History.txt
PuertoRico-WhatToDo.txt
PuertoRico-WhereToGo.txt
Vallarta-History.txt
```

In this case, I'm playing the role of a spain fanatic trying to look for any and all reference of the country in the berlitz 2. It just lists the file names which is useful for a big picture view of what files fit the criteria.

Option 2: grep -c
---
Example 3:
---
```
grep "e" -c -i  Barcelona-WhatToDo.txt 
39
```

grep -c; this flag simply just counts the number of matches. This is super useful if you want to see how many times a word actually shows up somewhere without having to manually count the output from a normal grep command. In the above example, I’m trying to find out if the letter “E” is truly the most used vowel in a document. I use grep -c to count up the instances of E and compare it to the output of the other vowels. I add -i to make it case insensitive. The Other vowels (A,I,O,U) were 41,40,42, and 35 respectively, which disproved my hypothesis.

Example 4:
----

```
grep -c -i “food” *.txt


Algarve-History.txt:0
Algarve-Intro.txt:0
Algarve-WhatToDo.txt:0
Algarve-WhereToGo.txt:0
Amsterdam-History.txt:1
Amsterdam-Intro.txt:0
Amsterdam-WhatToDo.txt:0
Amsterdam-WhereToGo.txt:1
Athens-History.txt:0
Athens-Intro.txt:1
Athens-WhatToDo.txt:4
Athens-WhereToGo.txt:1
Bahamas-History.txt:1
Bahamas-Intro.txt:0
Bahamas-WhatToDo.txt:0
Bahamas-WhereToGo.txt:2
Bali-History.txt:0
Bali-WhatToDo.txt:0
Bali-WhereToGo.txt:5
Barcelona-History.txt:0
Barcelona-WhatToDo.txt:2
Barcelona-WhereToGo.txt:3
Beijing-History.txt:0
Beijing-WhatToDo.txt:1
Beijing-WhereToGo.txt:3
Berlin-History.txt:1
Berlin-WhatToDo.txt:2
Berlin-WhereToGo.txt:2
Bermuda-history.txt:3
Bermuda-WhatToDo.txt:2
Bermuda-WhereToGo.txt:2
Boston-WhereToGo.txt:3
Budapest-History.txt:0
Budapest-WhatToDo.txt:1
Budapest-WhereoGo.txt:0
California-History.txt:1
California-WhatToDo.txt:0
California-WhereToGo.txt:8
Canada-History.txt:1
Canada-WhereToGo.txt:7
CanaryIslands-History.txt:0
CanaryIslands-WhatToDo.txt:1
CanaryIslands-WhereToGo.txt:2
Cancun-History.txt:2
Cancun-WhatToDo.txt:0
Cancun-WhereToGo.txt:2
China-History.txt:1
China-WhatToDo.txt:0
China-WhereToGo.txt:9
CostaBlanca-History.txt:0
CostaBlanca-WhatToDo.txt:4
Costa-History.txt:0
Costa-WhatToDo.txt:1
Costa-WhereToGo.txt:3
Crete-History.txt:1
Crete-WhatToDo.txt:0
Crete-WhereToGo.txt:2
CstaBlanca-WhereToGo.txt:1
Cuba-History.txt:1
Cuba-WhatToDo.txt:1
Cuba-WhereToGo.txt:2
Nepal-History.txt:0
Nepal-WhatToDo.txt:3
Nepal-WhereToGo.txt:2
NewOrleans-History.txt:2
Paris-WhatToDo.txt:4
Paris-WhereToGo.txt:3
Poland-History.txt:1
Poland-WhatToDo.txt:0
Portugal-History.txt:0
Portugal-WhatToDo.txt:1
Portugal-WhereToGo.txt:1
PuertoRico-History.txt:0
PuertoRico-WhatToDo.txt:0
PuertoRico-WhereToGo.txt:4
Vallarta-History.txt:0
Vallarta-WhatToDo.txt:3
Vallarta-WhereToGo.txt:12
```

Here I play the role of an obsessive gastrologist and try to find every file in the berlitz2 directory that mentions “food”; it lists out the count for each document individually which would be super useful if you were trying to rank the count for each of them. 

Option 3: grep -v
---

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

If we needed to censor all of our Non-fiction works by returning all chapters without the f-word in them, it would look something like the above; -v inverst the search for everything without the n-word in it. 


Option 4: -r
---

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

If you’re a person who can’t get enough drama and wants to keep up date with all of the ancient drama, this command is for you. It returns every file in the entire directory in which the word "drama" is inside. 

