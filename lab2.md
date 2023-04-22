# Lab Report 2 - Servers and Bugs
## Part 1
** StringServer code **
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler{
    String result = "";
    // /add-message?s=<string>
    public String handleRequest(URI url){
        if (url.getPath().equals("/")){
            return result; 
        }
        else if (url.getPath().contains("/add-message")){
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")){
                result += parameters[1] + "\n";
                return result; 
            }
            return "404 Not Found!";
        }
        else{
            return "404 Not Found!";
        }
    }
}
public class StringServer {
    public static void main(String[] args) throws IOException{
        if (args.length == 0){
            System.out.println("Missing port number!");
            return;
        }
        int port = Integer.parseInt(args[0]);
        Server.start(port, new Handler());
    }  
}
```
![Image](firstCommand.png)
The handleRequest method is called because a port is created and once you change the path and query, it prints out the message in the url query.
The argument is the url of type URI after the port number. First you get the path and if it equals to `/add-message` then you split the query by the equal sign and if the first index of the query array is `s`, then print out the second index of the query array. In this case, the url is `/add-message?s=hi` so the method identified the path which is `/add-message` and splits the query into `s` and `hi`. In this case, `s` equals to `s` so the method returns `hi`. 
The result changes by changing the query, specifically the part after the equal sign. It returns a new request based on the code: `result += parameters[1] + "\n";` which would be result += "hi" + "\n".

![Image](secondCommand.png)
The handleRequest method is called.
The relevent arguements to this method are path and query. The values for path is `/add-message` and the query is  `s=hello`. The method splits the query string by the equal sign and creates an array of `"s", "hello"`. If the first index of this array equals to `s`, it prints out the second index of this array which is `hello`. 
The result changes by changing the query, specifically the part after the equal sign. It returns a new request based on the code: `result += parameters[1] + "\n";` which would be `result += hello + "\n"`
