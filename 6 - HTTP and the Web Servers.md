# **HTTP (HyperText Transfer Protocol)**

HTTP is the protocol used for transferring data on the web. It defines how messages are formatted and transmitted, and how web servers and browsers should respond to various requests.

1.  **What is HTTP?**
    
    -   HTTP is primarily text-based and enables communication between clients (web browsers) and servers.
        
    -   **Request-Response Cycle**: The client sends a request to the server, and the server responds with the requested resource (e.g., a webpage).
        
2.  **Types of HTTP Requests**:
    
    -   **GET**: Requests a resource (e.g., a webpage).
        
    -   **POST**: Sends data to the server (e.g., form submission).
        
    -   **PUT/DELETE**: Used for updating or deleting resources (more common in Web 2.0 and RESTful APIs).
        
3.  **HTTP Response**:
    
    -   The server sends a response to the client, which typically includes:
        
        -   **Status Code**: Indicates the result of the request (e.g., 200 OK, 404 Not Found).
            
        -   **Headers**: Metadata like content type, caching information.
            
        -   **Body**: The actual data (e.g., HTML, images, JSON).
            

---

# **Web Servers**

A web server is a system that serves content over the web. It can be a physical machine or a software program that listens for incoming HTTP requests and sends back appropriate responses.

1.  **Basic Web Server**:  
    A basic web server can be as simple as a program that listens on a specific port, receives requests, and responds with content.
    
    -   **Example**: A simple HTTP server written in Python:
        
    
    ```bash
    python -m http.server
    ```
    
    This command runs a basic HTTP server that serves files from the current directory.
    
2.  **How Web Servers Work**:
    
    -   A web server listens on a fixed port (usually port 80 for HTTP or 443 for HTTPS).
        
    -   When it receives a request, it processes the request (usually by running code, accessing files, or querying a database) and returns a response.
        
    -   For example, when you request `GET /` in your browser, the web server might respond with an HTML document that your browser renders as a webpage.
        
3.  **Viewing Responses**:  
    You can use tools like `curl` to simulate HTTP requests and view the server's response. This can be helpful for debugging or testing APIs.
    
    **Example**:
    
    ```bash
    curl -v http://localhost:8000
    ```
    
    This command shows the HTTP request and response details, including headers, status codes, and content.
    