# Lab Report 3: find
The ```find``` command is used to return all items under a directory that matches given criteria. There are many options that can be passed in to make the ```find``` command return exactly what we want; in this lab report, I'll go over four of them.


## -type
I read about this option <a href="https://linuxhostsupport.com/blog/how-to-search-files-on-the-linux-terminal/"> here </a>.

We can filter ```find``` results by our desired type using the ```-type``` option. In the below command, using ```-type d``` specifies that we're only looking for *subdirectories* under the path ```written_2/non-fiction```. Notice that the ```written_2/non-fiction``` path itself is included in the returned list.
```
(base) MacBook-Pro-101:skill-demo1-data jimmy$ find written_2/non-fiction -type d
written_2/non-fiction
written_2/non-fiction/OUP
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Rybczynski
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Castro
(base) MacBook-Pro-101:skill-demo1-data jimmy$ 
```

We can modify the ```-type``` option to return a list of all files instead, by replacing ```-type d``` with ```-type f```. The below command demonstrates searching for and returning all files under the ```writtern_2/non-fiction``` path. This is useful when we don't want anything but files in our results.
```
(base) MacBook-Pro-101:skill-demo1-data jimmy$ find written_2/non-fiction -type f
written_2/non-fiction/.DS_Store
written_2/non-fiction/OUP/Berk/ch2.txt
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Berk/CH4.txt
written_2/non-fiction/OUP/Berk/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch2.txt
written_2/non-fiction/OUP/Abernathy/ch3.txt
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch6.txt
written_2/non-fiction/OUP/Abernathy/ch8.txt
written_2/non-fiction/OUP/Abernathy/ch9.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
written_2/non-fiction/OUP/Abernathy/ch14.txt
written_2/non-fiction/OUP/Rybczynski/ch2.txt
written_2/non-fiction/OUP/Rybczynski/ch3.txt
written_2/non-fiction/OUP/Rybczynski/ch1.txt
written_2/non-fiction/OUP/Kauffman/ch3.txt
written_2/non-fiction/OUP/Kauffman/ch1.txt
written_2/non-fiction/OUP/Kauffman/ch4.txt
written_2/non-fiction/OUP/Kauffman/ch5.txt
written_2/non-fiction/OUP/Kauffman/ch7.txt
written_2/non-fiction/OUP/Kauffman/ch6.txt
written_2/non-fiction/OUP/Kauffman/ch8.txt
written_2/non-fiction/OUP/Kauffman/ch9.txt
written_2/non-fiction/OUP/Kauffman/ch10.txt
written_2/non-fiction/OUP/Fletcher/ch2.txt
written_2/non-fiction/OUP/Fletcher/ch1.txt
written_2/non-fiction/OUP/Fletcher/ch5.txt
written_2/non-fiction/OUP/Fletcher/ch6.txt
written_2/non-fiction/OUP/Fletcher/ch9.txt
written_2/non-fiction/OUP/Fletcher/ch10.txt
written_2/non-fiction/OUP/Castro/chR.txt
written_2/non-fiction/OUP/Castro/chP.txt
written_2/non-fiction/OUP/Castro/chQ.txt
written_2/non-fiction/OUP/Castro/chB.txt
written_2/non-fiction/OUP/Castro/chC.txt
written_2/non-fiction/OUP/Castro/chA.txt
written_2/non-fiction/OUP/Castro/chV.txt
written_2/non-fiction/OUP/Castro/chW.txt
written_2/non-fiction/OUP/Castro/chM.txt
written_2/non-fiction/OUP/Castro/chZ.txt
written_2/non-fiction/OUP/Castro/chL.txt
written_2/non-fiction/OUP/Castro/chN.txt
written_2/non-fiction/OUP/Castro/chY.txt
written_2/non-fiction/OUP/Castro/chO.txt
(base) MacBook-Pro-101:skill-demo1-data jimmy$ 
```

## -s
I read about this option from the built-in manual for ```find```, using the command ```man find```.

The ```-s``` option returns the results of ```find``` in sorted order. The below command demonstrates sorting the contents of ```written_2/non-fiction/OUP/Abernathy```. Notice that "ch14" and "ch15" come before "ch2," as the items are compared as Strings instead of numbers.
```
(base) MacBook-Pro-101:skill-demo1-data jimmy$ find -s written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch14.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
written_2/non-fiction/OUP/Abernathy/ch2.txt
written_2/non-fiction/OUP/Abernathy/ch3.txt
written_2/non-fiction/OUP/Abernathy/ch6.txt
written_2/non-fiction/OUP/Abernathy/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch8.txt
written_2/non-fiction/OUP/Abernathy/ch9.txt
(base) MacBook-Pro-101:skill-demo1-data jimmy$
```
When a directory has many subdirectories, it may be useful to sort them by alphabetical order, and ```-s``` does the job. The below command demonstrates sorting all of ```written_2/non-fiction/OUP/```'s subdirectories in alphabetical order.
```
(base) MacBook-Pro-101:skill-demo1-data jimmy$ find -s written_2/non-fiction/OUP/ -type d
written_2/non-fiction/OUP/
written_2/non-fiction/OUP//Abernathy
written_2/non-fiction/OUP//Berk
written_2/non-fiction/OUP//Castro
written_2/non-fiction/OUP//Fletcher
written_2/non-fiction/OUP//Kauffman
written_2/non-fiction/OUP//Rybczynski
(base) MacBook-Pro-101:skill-demo1-data jimmy$
````

## -name

I read about this option <a href="https://linuxhostsupport.com/blog/how-to-search-files-on-the-linux-terminal/"> here </a>.

The ```-name``` option allows us to further filter our ```find``` results to match a certain name. It takes one input, the name of the desired item. The below command demonstrates searching for the ```'IntroMalaysia.txt'``` file, and the output confirms its existence.
```
(base) MacBook-Pro-101:skill-demo1-data jimmy$ find written_2/travel_guides/berlitz1 -type f -name 'IntroMalaysia.txt'
written_2/travel_guides/berlitz1/IntroMalaysia.txt
(base) MacBook-Pro-101:skill-demo1-data jimmy$ 
```

We can also try searching for a file that doesn't exist, like ```"IntroWakanda.txt"```. Nothing will be returned.
```
(base) MacBook-Pro-101:skill-demo1-data jimmy$ find written_2/travel_guides/berlitz1 -type f -name 'IntroWakanda.txt'
(base) MacBook-Pro-101:skill-demo1-data jimmy$ 
```

The two commands I just showed aren't too useful, as all they could do is check whether a file matching a given name exists or not. To expand on this, we can use the command line asterisk to return *all* items whose names include our input. The below command demonstrates using the ```-name``` option to return all files under the ```written_2/travel_guides/berlitz1``` path whose names begin with the string "Intro."
```
(base) MacBook-Pro-101:skill-demo1-data jimmy$ find written_2/travel_guides/berlitz1 -type f -name 'Intro*'
written_2/travel_guides/berlitz1/IntroMalaysia.txt
written_2/travel_guides/berlitz1/IntroEdinburgh.txt
written_2/travel_guides/berlitz1/IntroDublin.txt
written_2/travel_guides/berlitz1/IntroFrance.txt
written_2/travel_guides/berlitz1/IntroMadeira.txt
written_2/travel_guides/berlitz1/IntroIbiza.txt
written_2/travel_guides/berlitz1/IntroIsrael.txt
written_2/travel_guides/berlitz1/IntroMadrid.txt
written_2/travel_guides/berlitz1/IntroLosAngeles.txt
written_2/travel_guides/berlitz1/IntroJerusalem.txt
written_2/travel_guides/berlitz1/IntroLasVegas.txt
written_2/travel_guides/berlitz1/IntroIstanbul.txt
written_2/travel_guides/berlitz1/IntroHongKong.txt
written_2/travel_guides/berlitz1/IntroFWI.txt
written_2/travel_guides/berlitz1/IntroJamaica.txt
written_2/travel_guides/berlitz1/IntroGreek.txt
written_2/travel_guides/berlitz1/IntroItaly.txt
written_2/travel_guides/berlitz1/IntroIndia.txt
written_2/travel_guides/berlitz1/IntroEgypt.txt
written_2/travel_guides/berlitz1/IntroLakeDistrict.txt
written_2/travel_guides/berlitz1/IntroMallorca.txt
written_2/travel_guides/berlitz1/IntroJapan.txt
(base) MacBook-Pro-101:skill-demo1-data jimmy$ 
```

## -size

I read about this option <a href="https://linuxhostsupport.com/blog/how-to-search-files-on-the-linux-terminal/"> here </a>.

We can use the ```-size``` options to only return the files larger than or smaller than a given size. This could be useful when identifying particularly large files that are taking up a lot of space. In the below command, we are searching only for files under 10 kilobytes, denoted by ```-10k```.
```(base) MacBook-Pro-101:skill-demo1-data jimmy$ find written_2/non-fiction/OUP/ -type f -size -10k
written_2/non-fiction/OUP//Castro/chQ.txt
written_2/non-fiction/OUP//Castro/chW.txt
written_2/non-fiction/OUP//Castro/chZ.txt
written_2/non-fiction/OUP//Castro/chN.txt
written_2/non-fiction/OUP//Castro/chY.txt
written_2/non-fiction/OUP//Castro/chO.txt
(base) MacBook-Pro-101:skill-demo1-data jimmy$
```

We can also search for files larger than a given size or in between two sizes. The below command demonstrates searching for files larger than 50 kilobytes but smaller than 1 megabyte, denoted by ```+50k``` and ```-1M```, respectively.
```
(base) MacBook-Pro-101:skill-demo1-data jimmy$ find written_2/non-fiction/OUP/ -type f -size +50k -size -1M
written_2/non-fiction/OUP//Berk/ch2.txt
written_2/non-fiction/OUP//Berk/ch1.txt
written_2/non-fiction/OUP//Berk/CH4.txt
written_2/non-fiction/OUP//Berk/ch7.txt
written_2/non-fiction/OUP//Abernathy/ch8.txt
written_2/non-fiction/OUP//Rybczynski/ch3.txt
written_2/non-fiction/OUP//Kauffman/ch3.txt
written_2/non-fiction/OUP//Kauffman/ch1.txt
written_2/non-fiction/OUP//Kauffman/ch4.txt
written_2/non-fiction/OUP//Kauffman/ch6.txt
written_2/non-fiction/OUP//Kauffman/ch8.txt
written_2/non-fiction/OUP//Kauffman/ch9.txt
written_2/non-fiction/OUP//Kauffman/ch10.txt
written_2/non-fiction/OUP//Fletcher/ch2.txt
written_2/non-fiction/OUP//Fletcher/ch6.txt
written_2/non-fiction/OUP//Fletcher/ch9.txt
written_2/non-fiction/OUP//Castro/chM.txt
(base) MacBook-Pro-101:skill-demo1-data jimmy$ 
```
