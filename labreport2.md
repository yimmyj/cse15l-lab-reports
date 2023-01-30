## PART ONE

Here's the code lol

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
<br>
<img width="699" alt="Screen Shot 2023-01-28 at 8 34 00 PM" src="https://user-images.githubusercontent.com/69327109/215305069-47497de3-c0f5-4ff2-bf6e-40fbd48857b3.png">

The method called by this request is ```handleRequest```. The relevant argument to this method is ```url```, which is a Java URI object. Relevant fields of  the class include:
- the ```display``` String, which is empty
- the ```url``` URI, which is set to ```localhost:2023/add-message?s=hello world```;. 
- an array of Strings named ```parameters```, which is initialized as ```["s", "hello world"]```

The field of class changed by this request is the ```display``` String, which is changed to "hello world".
<br>
<img width="489" alt="Screen Shot 2023-01-28 at 8 34 15 PM" src="https://user-images.githubusercontent.com/69327109/215305078-9b7a0fde-3912-407d-b921-7bd04e8b0fff.png">

The method called by this request is ```handleRequest```. The relevant argument to this method is ```url```, which is a Java URI object. Relevant fields of  the class include:
- the ```display``` String, which is currently set to "hello world" by the previous request.
- the ```url``` URI, which is set to ```localhost:2023/add-message?s=goodbye world```;. 
- an array of Strings named ```parameters```, which is initialized as ```["s", "goodbye world"]```

The field of class changed by this request is the ```display``` String, which is changed to "hello world" + \n + "goodbye world".
<br>
