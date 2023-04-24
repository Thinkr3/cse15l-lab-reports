# Lab 2 - Servers and Bugs 🐛
## Part 1: Server Setup 💻
Here's a simple way to create a java web server and have it display text on screen.
### Server.java 📝
```
// A simple web server using Java's built-in HttpServer

// Examples from https://dzone.com/articles/simple-http-server-in-java were useful references

import java.io.IOException;
import java.io.OutputStream;
import java.net.InetSocketAddress;
import java.net.URI;

import com.sun.net.httpserver.HttpExchange;
import com.sun.net.httpserver.HttpHandler;
import com.sun.net.httpserver.HttpServer;

interface URLHandler {
    String handleRequest(URI url);
}

class ServerHttpHandler implements HttpHandler {
    URLHandler handler;
    ServerHttpHandler(URLHandler handler) {
      this.handler = handler;
    }
    public void handle(final HttpExchange exchange) throws IOException {
        // form return body after being handled by program
        try {
            String ret = handler.handleRequest(exchange.getRequestURI());
            // form the return string and write it on the browser
            exchange.sendResponseHeaders(200, ret.getBytes().length);
            OutputStream os = exchange.getResponseBody();
            os.write(ret.getBytes());
            os.close();
        } catch(Exception e) {
            String response = e.toString();
            exchange.sendResponseHeaders(500, response.getBytes().length);
            OutputStream os = exchange.getResponseBody();
            os.write(response.getBytes());
            os.close();
        }
    }
}

public class Server {
    public static void start(int port, URLHandler handler) throws IOException {
        HttpServer server = HttpServer.create(new InetSocketAddress(port), 0);

        //create request entrypoint
        server.createContext("/", new ServerHttpHandler(handler));

        //start the server
        server.start();
        System.out.println("Server Started! Visit http://localhost:" + port + " to visit.");
    }
}
```

### StringServer.java 📝
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String content = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("%s", content);
        } else if (url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    content += parameters[1] + "\n";
                    return String.format("%s", content);
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

### String Server Example 🧪
#### Blank Start Image ⬜
- Initialization
    - A String `contents` is initilized and will be kept in memoery as long as the server is active.
    - Nothing was called in this image I just called the standard homepage `http://localhost:4000`
- Which methods in your code are called?
    - When the page is loaded with that URL, `handleRequest(URI url)` is called.
    - `url.getPath()` is used to read the URL in a string format.
    - `.equals()` is used in the if statements to compare the contents of the URL to related functions in the program like `/add-message`.
    - `String.format()` is optional here but it is helpful to add as it formats any data inputed into the query as a string.
- What are the relevant arguments to those methods, and the values of any relevant fields of the class?
    - An if statement is called that checks the arguments in the URL path.
    - The first path checks if the path only has a `/` (This is true because blank paths have an implcit `/`)
    - This if branch returns the String variable `content`.
- How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
    - No values where changed in this example call because no queries were added to the path.
- <img src="img/blank.png" height="300" width="500">

#### Input Image 📜
- Initialization
    - Using this query `http://localhost:4000/add-message?s=Osmanthus%20wine%20tastes%20the%20same%20as%20I%20remember` I was able to append `Osmanthus wine tastes the same as I remember` to my current output stored on the webpage.
- Which methods in your code are called?
    - When the page is loaded with that URL, `handleRequest(URI url)` is called.
    - `getPath()` is used to read the URL in a string format.
    - `.equals()` is used in the if statements to compare the contents of the URL to related functions in the program like `/add-message`.
    - `getQuery()` is used to find the `?` in the path and read everything after the `?`.
    - `.split` is used to parse through the content so only the specific message is added to `content`.
    - `String.format()` is optional here but it is helpful to add as it formats any data inputed into the query as a string.

- What are the relevant arguments to those methods, and the values of any relevant fields of the class?
    - An if statement is called that parses the content after the domain.
    - The first branch in the if statement checks if the path only has a `/` (This is false) ❌
    - The second branch in the if statement checks if the path has `/add-message` (This is true) ✅
    - Then the branch gets the query using `getQuery()` and parses the content to find the intended user input.
    - This if branch concludes with appending `Osmanthus wine tastes the same as I remember \n` to the `content` variable. The `\n` is very important because it allows us to append more lines with `/add-message`.
- How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
    - The empty string (`""`) in the `content` variable was appended with `Osmanthus wine tastes the same as I remember \n`.
- <img src="img/first-line.png" height="300" width="500">

#### Finished Image 🖼
Here's an example of what this program can do d=====(￣▽￣*)b !
- <img src="img/zhongli.png" height="300" width="500">