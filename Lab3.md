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
followed by the query `?s=addfirst`, where `s` is the paramter and `addfirst` is the value.

The one and only class variable is `total` which keeps track of our master string and updates it as we make additions.

This how the variable `total` gets changed with our call to `handleRequest()`. We first 
get the paramters from the query, and since it matches with the paramater "s", we 
look at it's value which is "addfirst". We then add `"\n" + [addfirst] ` to total 
and return it's updated form.


It's worth noting that no matter what we pass to the parameter `s`, it will get parsed as a string. This means 
our program won't crash if we give it unintended input like ints or null, as seen below:

***

![various](https://user-images.githubusercontent.com/106555298/214993264-b60f18d7-4124-4a93-9163-ccfcdca401db.png)


***

__Input 2__: `localhost:[port]/add-message?s=addfirst`

***

![Screenshot 5](https://user-images.githubusercontent.com/106555298/214993373-b10da2d8-2afb-4e0b-8abf-d60942088489.png)


***

`handleRequest(url)` is being called here again, except the `url` variable is slightly different. 
It has the same path and a valid string, but the paramter for the query is `p` instead of `s`.

The class variable total doesn't get changed here. Here's why:

Since we only want the user to pass in data under the "s" parameter, we make sure to monitor if they attempt 
to pass data under any other paramter. While this strictly wouldn't break our parameter, it's a bad idea to 
as they could pass in malicious code as the query string, or our code would break later if we had different 
querystrings for different things. In this instance, the server returns the message "String Not Valid".

***

PART 2
====

Failure-Inducing Input
----

```
@Test
public void testReverseInPlace{
int [] list1 = {12,48,24,55};
    ArrayExamples.reverseInPlace((list1));
    assertArrayEquals(new int [] {55,24,48,12}, list1);}
```
No Failure Input:
---
```
@Test 
	public void testReverseInPlace() {
    int[] palindrome = {1,2,1  };
    ArrayExamples.reverseInPlace(palindrome);
    assertArrayEquals(new int[]{1,2,1}, palindrome);
	}
```

The Symptom:

***

![junit](https://user-images.githubusercontent.com/106555298/215002199-cbcd24ef-f4e6-4416-9051-423d3d1a7365.png)


***

Bug (Before):
----

```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

***

Bug (After):
---

```
static void reverseInPlace(int[] arr) {
    int[] temp  = new int[arr.length];
    for (int i = 0; i < arr.length; i ++)
    {
        temp[i] = arr[arr.length - 1 - i];
        
    };
    
   
    for (int i = 0; i < temp.length; i++)
    {arr[i] = temp[i];};
   
  }
```

__Why This Fixes The Issue__

Before, the list would iterate from the back to the front, but would reference the changed values at the front 
of the list in order to decide what to back at the front of the list. This effectively deletetd all record of the front 
of the list as it got overwritten. To fix this, we make a seperate deep copy of the original array going backwards
then reassign the original array to the deep one. It's important not to just change the reference of the original array
to the new one as the object at the original memory address stil gets returned, so it'll look like no changes were made at all. 
