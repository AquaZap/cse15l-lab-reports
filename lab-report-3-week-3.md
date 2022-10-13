Week 3 Lab Report

Part 1: SearchEngine implementation

import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    ArrayList<String> strings = new ArrayList<String>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Strings added: %s", strings.toString());
        }
        else if (url.getPath().contains("/add")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                    strings.add(parameters[1]);
                    return String.format("Added %s to the list of strings!", parameters[1]);
                }
            }
            return "404 Not Found!";
        }
        else {
            if (url.getPath().contains("/search")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    ArrayList<String> results = new ArrayList<String>();

                    for (int i = 0; i < strings.size(); i++) {
                        if(strings.get(i).contains(parameters[1])) {
                            results.add(strings.get(i));
                        }
                    }

                    if (results.size() == 0) {
                        return "Word cannot be found in any of the Strings";
                    }
                    else {
                        return results.toString();
                    }
                }
            }
            return "404 Not Found!";
        }

    }
}

class SearchEngine {

    public static void main(String[] args) throws IOException {
        if(args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}

I modeled my simple SearchEngine after the NumberServer class we were given. Like with that class, I first made a class within SearchEngine called Handler, implementing the method found within URLHandler, HandleRequest. It takes in a url, creates an empty ArrayList of strings to store added strings, and depending on the url, it will display a different message.

If we look at the first if statement, if(url.getPath().equals("/")), it's looking for whether or not the path is empty. Given that it is, it will merely return the Strings that have been added to the ArrayList via the toString(). 

Given that the path is not empty, it then checks if it contains "/add" with the following else if statement. If it does, then it will create a new String array called parameters by splitting the query at the "=". So if the entire url were "localhost:4000/add?s=apple" then parameters would be ["s", "apple"]. It then checks if that first element within parameters is "s". If it is, then it will add the second element within parameters to the final ArrayList of strings, and return a message saying that that string was added to the list. If the first element is not "s" it will return a 404 not found message.

Finally, if the path is not empty or does not contain "/add" then we assume it contains "/search" (we have an if statement within the else statement to check this and if it fails this check, it will return another 404 error message). Within this else statement we create another String array called parameters and split the query at the "=" once again. We also create a new ArrayList of Strings called results. Then, we loop through all of the added strings and see if they contain the 2nd element within parameters. If the current element does, then we add it to results, and if not the loop runs until it goes through all of the added strings. If by the end of the loop, the size of results = 0, then we return a message saying that the word cannot be found. Otherwise, we return results using the toString() method.

The main method of my SearchEngine does the same thing as NumberServer. It sets a server port given the url, and starts a new server taking in the port and a new Handler as its parameters. If no port was given, it returns a proper error message.

Part 2:


