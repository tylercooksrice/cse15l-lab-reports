### Lab Report 2 ###


**Part 1**
---

*Code for String Server*
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    
        int count = 1;
        String[] words = new String[2];

        public String handleRequest(URI url) {
            if (url.getPath().equals("/")) {
                if (count == 1) {
                    words[1]= "empty";
                    return String.format("This is your added string list\n%s", words[1]); 
                } 
            return String.format("This is your added string list\n%s", words[1]);    
            } else {
                if (url.getPath().contains("/add-messages")) {
                    String[] parameters = url.getQuery().split("=");
                        if (parameters[0].equals("s")) {
                            words[0] = String.format("%d. %s\n", count, parameters[1]); 
                            count++;
                            if (count == 2) {
                                words[1]= "";
                            }
                            words[1] = words[1] + words[0];
                            return words[1];
                        }
                    }
            } 
            return "404 Not Found!";
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

*after /add-message?s=hello command*
![Image](Add_Messages-hello.png)

- The handleRequest method is called according to main. 
- The revelant argument made was the object URI url. In addition, to the object URI url as an argument, the url link itself would need the
  /add-messages/s?=hello after localhost:4000 to add hello onto the stringServer's string list.
- No value changed were changed because hello is a singular string variable, therefore no changes were needed.

*after /add-message?s=How are you? command*
![Image](Add_Messages-How-are-you.png)

- The handleRequest method is called according to main. 
- The revelant argument made was the object URI url. Futhermore, to the object URI url as an argument, the url link itself would need the
  /add-messages?s=How%20are%20you after localhost:4000 to add How are you onto the stringServer's string list.
- Spaces got changed into percentage signs in the url link.


**Part 2**
---

- The path to the private key for your SSH key login for ieng6
![Image](Private_Address.png)

- The path to the public key for your SSH key login for ieng6
![Image](Public_Address.png)

- Terminal interaction without password when logging into ieng6
![Image](terminal_no_login.png)

**Part 3**
---

From lab of week two and three, I learned how to build and run a server, which was something I have always wanted to learn, and it was very cool to see what can be done by manipulating the URL paths. Using a remote computer was also a new concept that I learned because usually I would run every program from my own computer. It was cool to see how a remote computer would work and how similar it was to a personal computer, but at the same time, what the differences was.


