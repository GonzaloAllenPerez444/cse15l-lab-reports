Lab 3 Lab Report
========

By Gonzalo Allen-Perez
-----

PART 1 
-----

Here's the Code for StringServer.java. It has two classes, StringServer, which starts the server on the port given by the user, and Handler, which _handles_ the specific request in the url.

```

import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    
    String total = "";
    

    public String handleRequest(URI url) {
        
                if (url.getPath().contains("/add-message")) //checks if the path is right
                {

                    String[] parameters = url.getQuery().split("="); //splits query into the key and value
                    if (parameters[0].equals("s"))
                        {
                            //returns a newline plus the data entered in the query
                            total += "\n" + parameters[1];
                            return total;
                        };
                    //if the path is right, but the query key is off, return this
                    return "String not Valid";
                }
                //finally, if the path is wrong, return a 404
                else {return "404- Page Not Found!";}
            
            
    }
}
public class StringServer {
 //This just starts the server in the port given in the first CL arg
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
***
Here's an image of it if it's easier to look at:

***

![StringServerCode](https://user-images.githubusercontent.com/106555298/214990735-72132937-5b9e-454c-992b-5587f59dc917.png)


***

My Server in Action
----

Here are two requests to the server and what is going on

***

__Input 1__: `localhost:[port]/add-message?s=addfirst`

***

![Screenshot1](https://user-images.githubusercontent.com/106555298/214988021-ab601de0-4723-484a-8984-786e736af3ca.png)

*** 

The methods being called here is `public String handleRequest(URI url)`. 
The argument, `url` is the url starting with the path `add-message` 
followed by the query `?s=addfirst`, where `s` is the key and `addfirst` is the value.

The one and only class variable is `total` which keeps track of our master string and updates it as we make additions.

This how the variable `total` gets changed with our call to `handleRequest()`. We first 
get the paramters from the query, and since it matches with the paramater "s", we 
look at it's value which is "addfirst". We then add `"\n" + [addfirst] ` to total 
and return it's updated form.


It's worth noting that no matter what we pass to the parameter `s`, it will get parsed as a string. This means 
our program won't crash if we give it unintended input like ints or null, as seen below:

***

![Screenshot3](https://user-images.githubusercontent.com/106555298/214991694-98fe92a2-d07e-46a8-90e0-9be83587daa2.png)


***


