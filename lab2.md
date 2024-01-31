Part 1
=========	

ChatServer code:
```
import java.io.IOException;
import java.net.URI;
import java.util.*;


class Handler implements URLHandler {

    ArrayList<String> chatHistory = new ArrayList<String>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("&");
            String[] messageInput = parameters[0].split("=");
            String[] userInput = parameters[1].split("=");
            if (messageInput[0].equals("s") && userInput[0].equals("user")) {
                String messageEntry = userInput[1] + ": " + messageInput[1] + "\n";
                chatHistory.add(messageEntry);
            }
        } 
        else {
            return "404 Not Found!";
        }

        String output ="";
        for (String entryString: chatHistory) {
            output += entryString;
        }
        return output; 
    }
}
class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number!");
            return;
        }
        int port = Integer.parseInt(args[0]);
        Server.start(port, new Handler());
    }
}
```

First screenshot:
---------	

![Image](lab2_p1_screenshot1.png)

Which methods in your code are called?
* The first method that is called in my code is the main method in the `ChatServer` class, which sets up what port the web server will be running on. This is done by calling the main method of `Server.java`, which uses the port number and a new Handler object, and this new object calls the `ServerHttpHandler` constructor method in the class `ServerHttpHandler`, which is a new instance of `HttpHandler`. From here a new server is created in the main method of `Server.java`.  
* The next method that is called is the `handleRequest` method in the `Handler` class in `ChatServer`, which is implementing the method from the interface `URLHandler`. This happens once a path and query are added to the URL is from the `ChatServer` class. 

What are the relevant arguments to those methods, and the values of any relevant fields of the class?
* For the main method of `ChatServer`, it takes the command line argument as the port number.  
* The main method of `Server` takes a port number and URLHandler object.
* The `ServerHttpHandler` method of the `ServerHttpHandler` class initializes the URLHandler object that is in the argument.
* The `handleRequest` method in `ChatServer` takes in a URL as the argument and returns a String based on the code written in the method.
* One relevant field of the class is the `ArrayList` variable, `chatHistory`, which stores all the formatted Strings of the users and each message they've sent. 

How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
The `ArrayList` `chatHistory` changes with this specific request since it adds the String `yash: How+are+you` to the existing ArrayList that also holds all the previous chats sent from any specified user, such as `jpolitz: Hello`, an example chat previously requested/sent. 

Second screenshot:
---------	

![Image](lab2_p1_screenshot2.png)

Which methods in your code are called?
* The first method that is called in my code is the main method in the `ChatServer` class, which sets up what port the web server will be running on. This is done by calling the main method of `Server.java`, which uses the port number and a new Handler object, and this new object calls the `ServerHttpHandler` constructor method in the class `ServerHttpHandler`, which is a new instance of `HttpHandler`. From here a new server is created in the main method of `Server.java`.  
* The next method that is called is the `handleRequest` method in the `Handler` class in `ChatServer`, which is implementing the method from the interface `URLHandler`. This happens once a path and query are added to the URL is from the `ChatServer` class. 

What are the relevant arguments to those methods, and the values of any relevant fields of the class?
* For the main method of `ChatServer`, it takes the command line argument as the port number.  
* The main method of `Server` takes a port number and URLHandler object.
* The `ServerHttpHandler` method of the `ServerHttpHandler` class initializes the URLHandler object that is in the argument.
* The `handleRequest` method in `ChatServer` takes in a URL as the argument and returns a String based on the code written in the method.
* One relevant field of the class is the `ArrayList` variable, `chatHistory`, which stores all the formatted Strings of the users and each message they've sent. 

How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
The `ArrayList` `chatHistory` changes with this specific request since it adds the String `yash: nice!` to the existing ArrayList that also holds all the previous chats sent from any specified user, such as `thrisha: Good!`, an example chat previously requested/sent. 

Part 2
=========	
The absolute path to the private key for your SSH key for logging into ieng6 (on your computer, an EdStem workspace, or on the home directory of the lab computer)

![Image](lab2_p2_ss1.png)

* When setting up my SSH key for easy access during the lab section, I made a public and private key to my course-specific account. 

The absolute path to the public key for your SSH key for logging into ieng6 (this is the one you copied to your account on ieng6, so it should be a path on ieng6's file system)

![Image](lab2_p2_ss2.png)

* When setting up my SSH key for easy access during the lab section, I made a public and private key to my course-specific account. 

A terminal interaction where you log into your ieng6 account without being asked for a password.

![Image](lab2_p2_ss3.png)

* when I type in `ssh tpraveen@ieng6.ucsd.edu` into my terminal on Visual Studio Code, it allows me to log into my ieng6 without it asking for my password. As you can see when I type in the `ls` command, I have access to two directories/folders that are available in my remote account.

Part 3
=========	
Something I learned from lab in week 2 or 3 that you didn't know before: I learned how the different parts of a URL each have their own function to get the right information to show on the website. Before learning what a query and a path were, URLs looked like a bunch of nonsense, but after understanding this information, I know how URLs are used in website development and how they function. Now when I'm on a website, I use what I've learned to try and break down the different parts of that website's URL to practice what I learned. 
