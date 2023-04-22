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
