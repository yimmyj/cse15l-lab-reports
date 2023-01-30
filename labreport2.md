# Lab Report 2
## Part One

Below is the code for the String Server:

```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    
    String display = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    display += parameters[1].trim() + "\n";
                    return display;
        }
                return "incorrect argument";
        }

         else {
            return display;
        }
    }
}

class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```

Here are two sample HTTP requests:

---
<img width="699" alt="Screen Shot 2023-01-28 at 8 34 00 PM" src="https://user-images.githubusercontent.com/69327109/215305069-47497de3-c0f5-4ff2-bf6e-40fbd48857b3.png">

The method called by this request is ```handleRequest```. The relevant argument to this method is ```url```, which is a Java URI object. Relevant fields of  the class include:
- the ```display``` String, which is empty
- the ```url``` URI, which is set to ```localhost:2023/add-message?s=hello world```;. 
- an array of Strings named ```parameters```, which is initialized as ```["s", "hello world"]```

The field of the class changed by this request is the ```display``` String, which is changed to ```"hello world"```.

---
<img width="489" alt="Screen Shot 2023-01-28 at 8 34 15 PM" src="https://user-images.githubusercontent.com/69327109/215305078-9b7a0fde-3912-407d-b921-7bd04e8b0fff.png">

The method called by this request is ```handleRequest```. The relevant argument to this method is ```url```, which is a Java URI object. Relevant fields of  the class include:
- the ```display``` String, which is currently set to ```"hello world"``` by the previous request.
- the ```url``` URI, which is set to ```localhost:2023/add-message?s=goodbye world```;. 
- an array of Strings named ```parameters```, which is initialized as ```["s", "goodbye world"]```

The field of the class changed by this request is the ```display``` String, which is changed to ```"hello world" + \n + "goodbye world"```.

## Part Two

We are using JUnit to test the buggy ```reverseInPlace``` method, which returns the average of the elements in the array after excluding its lowest element.``` Below is a test that fails:

```import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
  @Test
  public void testAverageRepeatedLowest() {
    double[] input1 = {10, 10, 10, 11, 12, 13};
    assertEquals(12, ArrayExamples.averageWithoutLowest(input1), 0.01);
  }
}
```

And here is a test that passes:

```import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
   @Test
  public void testAverageOneLowest() {
    double[] input1 = {10, 11, 12, 13};
    assertEquals(12, ArrayExamples.averageWithoutLowest(input1), 0.01);
  }
}
```

The screenshot below shows the result of running both tests; the ```testAverageOneLowest``` passes, while ```testAverageRepeatedLowest``` fails. In the second case, the symptom of the bug is that the method returns a value (7.2) much lower than expected (12). After some hand calculations, it can be seen that 7.2 is the value obtained by dividing the non-excluded terms' sum (36) by an incorrect length (5 instead of 3).
<img width="991" alt="Screen Shot 2023-01-29 at 6 45 06 PM" src="https://user-images.githubusercontent.com/69327109/215376719-aa25970d-cf8d-4a46-ae87-66c62fe1313b.png">

Because of this symptom, I concluded that the bug was that the code only accounts for the case that there is one unique lowest value in the array. Even if there were more than one lowest value, the code still erroneously calculated the average by dividing the sum of the non-excluded numbers by the *length of the array minus one*, rather than *the length of the array minus the number of times the lowest value appears*. Thus, I made the following change to my code:

### Before:
```
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }
  ```

### After:
```
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    double counter = 0;
    for(double num: arr) {
      if(num != lowest) { 
        sum += num; 
        counter++;
    }
    }
    return sum / (counter);
  }
 ```
 
 I changed the code such that instead of dividing the sum of the non-excluded values by ```arr.length-1```, it divides the sum by a ```double``` named ```counter``` that keeps track of the number non-excluded items. This fixes the bug described above. After making this change, both test cases pass.

## Part Three

I learned new things about computer science from both lab 2 and lab 3. In lab 2, I learned how URI's typed into a search bar are handled and processed by code, as well as how to make the browser respond to requests. In lab 3, I learned the difference between a *symptom* and a *bug* when describing erroneous code; I will begin using these terms in my vocabulary instead of describing everything as an "error." I also learned how buggy code can work perfectly fine for some inputs, and the importance of testing to make sure that code is actually correct.
