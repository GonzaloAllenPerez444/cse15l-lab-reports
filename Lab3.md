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
    
    ArrayList<String> masterList = new ArrayList<String>();
    

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
