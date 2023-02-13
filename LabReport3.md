command: Gep
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
