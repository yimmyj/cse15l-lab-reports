## Step 4: Log in

Keys pressed: ```<ctrl+v> <enter>``` 

I copied the ```ssh``` command from a Lab Report 1, and pasted it into the terminal.

<img width="1028" alt="Screen Shot 2023-02-26 at 9 38 57 PM" src="https://user-images.githubusercontent.com/69327109/221483234-0d9d2fdb-7192-46fb-ad8e-5e453139ae42.png">
<img width="1026" alt="Screen Shot 2023-02-26 at 9 39 11 PM" src="https://user-images.githubusercontent.com/69327109/221483263-b65c8099-5c60-47f0-8ec9-7b4e5f4432d4.png">

## Step 5: Clone Repository
Keys pressed: ```<up><up><up><up><up><enter>```

I had the ```git clone``` command saved in my bash history from a previous attempt, and I navigated to it using the up arrow.


<img width="990" alt="Screen Shot 2023-02-26 at 9 46 38 PM" src="https://user-images.githubusercontent.com/69327109/221484251-70a49c5f-b36e-4d81-bc93-869e2e908ff6.png">

## Step 6: Run tests, confirm they fail
Keys pressed: 

```cd lab7 <enter>```

I ```cd```'d into the newly cloned directory so that my saved JUnit commands, which did not use ```lab7/``` as part of the path, would run in the correct directory.

```ls <enter> ```

I used ```ls``` to ensure I was in the correct directory. This step is not necessary and could have been skipped to save a few miliseconds.

```<up><up><up><up><up><up><up><enter>```
```<up><up><up><up><up><up><up><enter>```

Both the ```javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java``` (compile) and ```java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests``` (run JUnit tests) commands were saved in my bash history from a previous run, so I used the up arrow to access them.

<img width="1364" alt="Screen Shot 2023-02-26 at 9 48 00 PM" src="https://user-images.githubusercontent.com/69327109/221484482-177b7113-b5a2-4d07-bc8d-a4bb23656ec7.png">

## Step 7: Fix the code

Keys pressed: ```nano L <tab> . j <tab>```

I open the buggy file using ```nano```. After hitting ```L```, I click ```<tab>``` to autocomplete the name to ```ListExamples```. (The name does not autocomplete to ```ListExamples.java``` because there is another file named ```ListExamplesTest.java```, and Bash does not know which file we are trying we are trying to refer to.) Therefore, I hit ```.j``` and ```<tab>``` again, which now autocompletes to the desired file ```ListExamples.java```.

<img width="546" alt="Screen Shot 2023-02-26 at 9 59 54 PM" src="https://user-images.githubusercontent.com/69327109/221486252-9b75b732-048a-4dc8-8b42-33e70f31d5cc.png">

Keys pressed: ```<ctrl> <W> <ctrl> <V>```
The ```nano``` menu says that ```<ctrl> <W>``` will allow you to find something in the file, and ```<ctrl> <V>``` will bring us to the bottom of the file.

<img width="1022" alt="Screen Shot 2023-02-26 at 10 06 24 PM" src="https://user-images.githubusercontent.com/69327109/221487242-fbdc1e31-f9d9-44c4-ba14-689570532c3d.png">

Keys pressed: ```<up> <up> <up> <up> <up> <up> <up> <right> <right> <right> <right> <right> <right> <right> <right> <right> <right> <right> <right> <delete> <2>```

This sequence of keys brings us to the error in the code, and fixes it.

<img width="1023" alt="Screen Shot 2023-02-26 at 10 08 57 PM" src="https://user-images.githubusercontent.com/69327109/221487590-22964bf3-d81a-48bb-a186-d205c071c13c.png">

Keys pressed: ```<ctrl> X y <enter>```

This sequence of keys saves the edits to the file and exits it.

## Step 8: Runs the code to demonstrate that the tests now pass

Keys pressed: ```<up> <up> <up> <enter>```

```javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java``` was saved in Bash history when I ran it to compile for the first time.

Keys pressed: ```<up> <up> <up> <enter>```

 ```java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests``` was saved in Bash history when I ran it to show my tests failed.
 
 <img width="1023" alt="Screen Shot 2023-02-26 at 10 16 25 PM" src="https://user-images.githubusercontent.com/69327109/221488682-be970895-9208-4055-acc2-8e61801bb64b.png">

## Step 9: Commits and pushes my changes

Commands: 

```git add . <enter>```

```git commit -m "hello" <enter>```

```git push origin <enter>```

This sequence of commands commits and pushes the changes to my Github account.

<img width="1010" alt="Screen Shot 2023-02-26 at 10 19 10 PM" src="https://user-images.githubusercontent.com/69327109/221489072-e31335f6-1cd9-4d94-b20d-723be71ef4ba.png">

 
 
