# Lab Report 3
## Part One

find -d
```
(base) MacBook-Pro-101:non-fiction jimmy$ find -d OUP/
OUP//Berk/ch2.txt
OUP//Berk/ch1.txt
OUP//Berk/CH4.txt
OUP//Berk/ch7.txt
OUP//Berk
OUP//Abernathy/ch2.txt
OUP//Abernathy/ch3.txt
OUP//Abernathy/ch1.txt
OUP//Abernathy/ch7.txt
OUP//Abernathy/ch6.txt
OUP//Abernathy/ch8.txt
OUP//Abernathy/ch9.txt
OUP//Abernathy/ch15.txt
OUP//Abernathy/ch14.txt
OUP//Abernathy
OUP//Rybczynski/ch2.txt
OUP//Rybczynski/ch3.txt
OUP//Rybczynski/ch1.txt
OUP//Rybczynski
OUP//Kauffman/ch3.txt
OUP//Kauffman/ch1.txt
OUP//Kauffman/ch4.txt
OUP//Kauffman/ch5.txt
OUP//Kauffman/ch7.txt
OUP//Kauffman/ch6.txt
OUP//Kauffman/ch8.txt
OUP//Kauffman/ch9.txt
OUP//Kauffman/ch10.txt
OUP//Kauffman
OUP//Fletcher/ch2.txt
OUP//Fletcher/ch1.txt
OUP//Fletcher/ch5.txt
OUP//Fletcher/ch6.txt
OUP//Fletcher/ch9.txt
OUP//Fletcher/ch10.txt
OUP//Fletcher
OUP//Castro/chR.txt
OUP//Castro/chP.txt
OUP//Castro/chQ.txt
OUP//Castro/chB.txt
OUP//Castro/chC.txt
OUP//Castro/chA.txt
OUP//Castro/chV.txt
OUP//Castro/chW.txt
OUP//Castro/chM.txt
OUP//Castro/chZ.txt
OUP//Castro/chL.txt
OUP//Castro/chN.txt
OUP//Castro/chY.txt
OUP//Castro/chO.txt
OUP//Castro
OUP/
```

```
(base) MacBook-Pro-101:non-fiction jimmy$ find -s OUP/
OUP/
OUP//Abernathy
OUP//Abernathy/ch1.txt
OUP//Abernathy/ch14.txt
OUP//Abernathy/ch15.txt
OUP//Abernathy/ch2.txt
OUP//Abernathy/ch3.txt
OUP//Abernathy/ch6.txt
OUP//Abernathy/ch7.txt
OUP//Abernathy/ch8.txt
OUP//Abernathy/ch9.txt
OUP//Berk
OUP//Berk/CH4.txt
OUP//Berk/ch1.txt
OUP//Berk/ch2.txt
OUP//Berk/ch7.txt
OUP//Castro
OUP//Castro/chA.txt
OUP//Castro/chB.txt
OUP//Castro/chC.txt
OUP//Castro/chL.txt
OUP//Castro/chM.txt
OUP//Castro/chN.txt
OUP//Castro/chO.txt
OUP//Castro/chP.txt
OUP//Castro/chQ.txt
OUP//Castro/chR.txt
OUP//Castro/chV.txt
OUP//Castro/chW.txt
OUP//Castro/chY.txt
OUP//Castro/chZ.txt
OUP//Fletcher
OUP//Fletcher/ch1.txt
OUP//Fletcher/ch10.txt
OUP//Fletcher/ch2.txt
OUP//Fletcher/ch5.txt
OUP//Fletcher/ch6.txt
OUP//Fletcher/ch9.txt
OUP//Kauffman
OUP//Kauffman/ch1.txt
OUP//Kauffman/ch10.txt
OUP//Kauffman/ch3.txt
OUP//Kauffman/ch4.txt
OUP//Kauffman/ch5.txt
OUP//Kauffman/ch6.txt
OUP//Kauffman/ch7.txt
OUP//Kauffman/ch8.txt
OUP//Kauffman/ch9.txt
OUP//Rybczynski
OUP//Rybczynski/ch1.txt
OUP//Rybczynski/ch2.txt
OUP//Rybczynski/ch3.txt
```

```
find non-fiction -type d -name 'OUP'
non-fiction/OUP
```
## -type
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

We can modify the ```-type``` option to return a list of all files instead, by replacing ```-type d``` with ```-type f```. The below command demonstrates searching for and returning all files under the ```writtern_2/non-fiction``` path.
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

## -name

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
