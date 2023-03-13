# Lab Report 5: grep command
For my final lab report, I'll focus on another command we went over in Lab Report 3: ```grep```. The ```grep``` command is used to search for a specified pattern of characters either inside a file, or in all files under a directory. There are many options that can be passed in to make the ```grep``` command return exactly what we want; in this lab report, I'll go over four of them.

Note: The working directory used in this lab report is ```/Users/jimmy/Desktop/UCSD COURSEWORK/CSE 15L/docsearch/written_2```, or simply the ```docsearch/written_2``` folder from lab report 3.


## -r
I read about this option <a href="https://alvinalexander.com/linux-unix/recursive-grep-r-searching-egrep-find/"> here </a>.

Instead of having ```grep``` search through just one file or some set of files, we can have ```grep``` recursively search through files of all subdirectories using the ```-r``` option.

Below, I use ```grep``` to recursively find where the word "Bananas" occurs in the entire directory.
```
(base) jimmy@MacBook-Pro-101 written_2 % grep -r "Bananas" *
written_2/travel_guides/berlitz1/WhatToHongKong.txt:        nightlife, have become almost respectable. Joe Bananas, 23 Luard Road,
(base) jimmy@MacBook-Pro-101 docsearch %
```

However, sometimes the files containing my specified word has too many extra words that I don't want, such as when I try to search recursively for "Bahamas:"
```quote
(base) jimmy@MacBook-Pro-101 written_2 % grep -r "Bahamas" * 
travel_guides/berlitz1/WhatToFWI.txt:        waters off the Bahamas, Puerto Rico, and the Virgin Islands, but the
travel_guides/berlitz2/Bahamas-WhereToGo.txt:It’s not the largest of the Bahamas islands and not 
the most stunningly beautiful, yet when most people think of the Bahamas they first think of 
New Providence or its major town, Nassau. The island is only 80 square miles in size yet 
180,000 of the 280,000 Bahamians lives here. The town and its port and international 
airport are the hub for every activity in the Bahamas. Government, administration, 
taxes, and furniture shipments for new homes all start
... and so on!!!
```
This is where another option comes in.

## -l
I read about this option <a href="https://www.geeksforgeeks.org/grep-command-in-unixlinux/"> here </a>. 

The ```-l``` option makes it so that only the names of the files containing a certain pattern are printed in the terminal, instead of the contents of the files.

For instance, if we wanted to neatly print all of the files mentioning the word "Bahamas," we can use ```-l``` as show below:
```
(base) jimmy@MacBook-Pro-101 written_2 % grep -rl "Bahamas" *
travel_guides/berlitz1/WhatToFWI.txt
travel_guides/berlitz2/Bahamas-WhereToGo.txt
travel_guides/berlitz2/Canada-WhereToGo.txt
travel_guides/berlitz2/Bahamas-Intro.txt
travel_guides/berlitz2/Bahamas-WhatToDo.txt
travel_guides/berlitz2/Bahamas-History.txt
(base) jimmy@MacBook-Pro-101 written_2 % 
```

With the same command, I can narrow my query down to only look for matching files in the travel_guides/berlitz2 subdirectory:
```
(base) jimmy@MacBook-Pro-101 written_2 % grep -rl "Bahamas" travel_guides/berlitz2
travel_guides/berlitz2/Bahamas-WhereToGo.txt
travel_guides/berlitz2/Canada-WhereToGo.txt
travel_guides/berlitz2/Bahamas-Intro.txt
travel_guides/berlitz2/Bahamas-WhatToDo.txt
travel_guides/berlitz2/Bahamas-History.txt
(base) jimmy@MacBook-Pro-101 written_2 % 
```

## -c
I read about this option <a href="https://www.geeksforgeeks.org/grep-command-in-unixlinux/"> here </a>. 

The ```-c``` option allows us count the number of lines in which specific pattern shows up in a file. For instance, running it on the ```travel_guides/berlitz2/Bahamas-WhereToGo.txt``` file will output 34, meaning that there are 34 lines in the files that contain the phrase "Bahamas"
```
(base) jimmy@MacBook-Pro-101 written_2 % grep -c "Bahamas" travel_guides/berlitz2/Bahamas-WhereToGo.txt
34
(base) jimmy@MacBook-Pro-101 written_2 % 
```

The ```-c``` option can be used alongside ```-r``` to display the number of lines in which a pattern appears for *every* file within a directory, as demonstrated below:
```
(base) jimmy@MacBook-Pro-101 written_2 % grep -cr "Bahamas" travel_guides/berlitz2
travel_guides/berlitz2/Portugal-History.txt:0
travel_guides/berlitz2/Berlin-WhereToGo.txt:0
travel_guides/berlitz2/Costa-History.txt:0
travel_guides/berlitz2/Amsterdam-WhereToGo.txt:0
travel_guides/berlitz2/Costa-WhereToGo.txt:0
travel_guides/berlitz2/Amsterdam-WhatToDo.txt:0
travel_guides/berlitz2/CostaBlanca-WhatToDo.txt:0
travel_guides/berlitz2/Barcelona-History.txt:0
travel_guides/berlitz2/Portugal-WhereToGo.txt:0
travel_guides/berlitz2/Boston-WhereToGo.txt:0
travel_guides/berlitz2/Poland-WhatToDo.txt:0
travel_guides/berlitz2/California-WhereToGo.txt:0
travel_guides/berlitz2/Cuba-WhatToDo.txt:0
travel_guides/berlitz2/Berlin-History.txt:0
travel_guides/berlitz2/Bahamas-WhereToGo.txt:34
travel_guides/berlitz2/Cancun-WhatToDo.txt:0
travel_guides/berlitz2/Bali-History.txt:0
travel_guides/berlitz2/Crete-WhereToGo.txt:0
travel_guides/berlitz2/Athens-History.txt:0
travel_guides/berlitz2/Berlin-WhatToDo.txt:0
travel_guides/berlitz2/Canada-WhereToGo.txt:1
travel_guides/berlitz2/Bali-WhereToGo.txt:0
travel_guides/berlitz2/Budapest-WhereoGo.txt:0
travel_guides/berlitz2/Barcelona-WhereToGo.txt:0
travel_guides/berlitz2/Athens-WhereToGo.txt:0
travel_guides/berlitz2/Paris-WhereToGo.txt:0
travel_guides/berlitz2/China-WhereToGo.txt:0
travel_guides/berlitz2/Bermuda-WhatToDo.txt:0
travel_guides/berlitz2/California-History.txt:0
travel_guides/berlitz2/Vallarta-History.txt:0
travel_guides/berlitz2/Budapest-WhatToDo.txt:0
travel_guides/berlitz2/Cancun-History.txt:0
travel_guides/berlitz2/PuertoRico-WhatToDo.txt:0
travel_guides/berlitz2/Vallarta-WhatToDo.txt:0
travel_guides/berlitz2/Bali-WhatToDo.txt:0
travel_guides/berlitz2/CostaBlanca-History.txt:0
travel_guides/berlitz2/CstaBlanca-WhereToGo.txt:0
travel_guides/berlitz2/NewOrleans-History.txt:0
travel_guides/berlitz2/PuertoRico-History.txt:0
travel_guides/berlitz2/Algarve-Intro.txt:0
travel_guides/berlitz2/Nepal-History.txt:0
travel_guides/berlitz2/China-History.txt:0
travel_guides/berlitz2/Canada-History.txt:0
travel_guides/berlitz2/Crete-History.txt:0
travel_guides/berlitz2/Portugal-WhatToDo.txt:0
travel_guides/berlitz2/Bahamas-Intro.txt:11
travel_guides/berlitz2/Amsterdam-History.txt:0
travel_guides/berlitz2/Bahamas-WhatToDo.txt:16
travel_guides/berlitz2/Barcelona-WhatToDo.txt:0
travel_guides/berlitz2/Algarve-WhatToDo.txt:0
travel_guides/berlitz2/PuertoRico-WhereToGo.txt:0
travel_guides/berlitz2/Cuba-WhereToGo.txt:0
travel_guides/berlitz2/Costa-WhatToDo.txt:0
travel_guides/berlitz2/Beijing-History.txt:0
travel_guides/berlitz2/Nepal-WhereToGo.txt:0
travel_guides/berlitz2/CanaryIslands-WhereToGo.txt:0
travel_guides/berlitz2/Bermuda-history.txt:0
travel_guides/berlitz2/CanaryIslands-History.txt:0
travel_guides/berlitz2/Amsterdam-Intro.txt:0
travel_guides/berlitz2/Crete-WhatToDo.txt:0
travel_guides/berlitz2/Algarve-WhereToGo.txt:0
travel_guides/berlitz2/Athens-Intro.txt:0
travel_guides/berlitz2/Algarve-History.txt:0
travel_guides/berlitz2/Poland-History.txt:0
travel_guides/berlitz2/Beijing-WhereToGo.txt:0
travel_guides/berlitz2/CanaryIslands-WhatToDo.txt:0
travel_guides/berlitz2/California-WhatToDo.txt:0
travel_guides/berlitz2/Budapest-History.txt:0
travel_guides/berlitz2/China-WhatToDo.txt:0
travel_guides/berlitz2/Athens-WhatToDo.txt:0
travel_guides/berlitz2/Nepal-WhatToDo.txt:0
travel_guides/berlitz2/Bermuda-WhereToGo.txt:0
travel_guides/berlitz2/Paris-WhatToDo.txt:0
travel_guides/berlitz2/Cuba-History.txt:0
travel_guides/berlitz2/Vallarta-WhereToGo.txt:0
travel_guides/berlitz2/Bahamas-History.txt:23
travel_guides/berlitz2/Beijing-WhatToDo.txt:0
travel_guides/berlitz2/Cancun-WhereToGo.txt:0
(base) jimmy@MacBook-Pro-101 written_2 %
```

## -n

If I wanted to know what line a certain pattern was found, I can use the ```-n``` option. Below, I demonstrate using the ```-n``` option with the recursive search ```-r``` to find the file in which the word "Bananas" appears, as well as print its line number.

```
(base) jimmy@MacBook-Pro-101 written_2 % grep -rn "Bananas" travel_guides
travel_guides/berlitz1/WhatToHongKong.txt:278:        nightlife, have become almost respectable. Joe Bananas, 23 Luard Road,
(base) jimmy@MacBook-Pro-101 written_2 % 
```
We now know that "Bananas" is on line 278 of the ```WhatToHongKong.txt``` file.

The ```-n``` option can also be used without ```-r``` to find where a pattern is located in one specific file. Below, I demonstrate searching for the word "southern" in the ```Algarve-Intro.txt``` file, which is located on lines 6, 7, and 16.
```
(base) jimmy@MacBook-Pro-101 written_2 % grep -n "southern" travel_guides/berlitz2/Algarve-Intro.txt
6:For much of the world, the Algarve is synonymous with Portugal, yet the Portuguese will tell you the exact opposite: the region has little in common with the rest of the country. The southern stretch of coast is more reminiscent of a North African landscape than a European one. It has no cosmopolitan cities, like Lisbon and Porto, which are farther north. Most of Portugal is known for quaint towns, medieval castles, and grand palaces. The Algarve is more recognizable for impenetrable blocks of tourist apartments, hotels, and meticulously manicured golf courses.
7:And beaches. Think Algarve and the mind pictures long, glorious stretches of golden sands, secluded coves framed by odd ochre-colored rock formations, and deep green waters. With about 160 km (100 miles) of coastline, Portugal’s southern province is one of Europe’s premier beach destinations. The occasionally chilly ocean is the Atlantic, but the Algarve has a sultry Mediterranean feel.
16:Following the Reconquest of Iberia by Christians, the Algarve led Portugal to glory and fortune. Prince Henry the Navigator established his legendary Navigation School along Portugal’s southern coast (financing expeditions with royalties from the Algarve fishing industry), and intrepid explorers set out in caravels from Lagos and Sagres. In the 15th and 16th centuries, they ushered in an Age of Discovery, rounding Africa’s Cape of Good Hope and eventually reaching India and the Pacific. Others found their way to the Americas and Brazil. Opening world trade routes across the globe, they established Portugal as a maritime superpower. Spices, gold, and diamonds flowed across the seas to Lisbon.
(base) jimmy@MacBook-Pro-101 written_2 %
```

This concludes my last CSE 15L lab report. I really enjoyed the content of this class. Thank you Professor Politz, TA's and tutors :)
