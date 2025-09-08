# **Architecture**

The architecture of applications defines how different components interact within the system. The two key architectural models covered are:

#### **Client-Server Architecture**:

-   **Server**: The server stores the data and provides it to clients when requested. It may also perform computations and handle business logic.
    
-   **Client**: The client is the end-user's device (e.g., computer, mobile phone) that requests data from the server. The client displays the data and allows user interaction.
    
-   **Example**: In a web app, when you open a webpage, your browser (the client) sends a request to a web server, which processes the request and sends back the requested data (the web page).
    

#### **Distributed (Peer-to-Peer) Architecture**:

-   **Peers**: In a distributed system, peers act as both clients and servers. They share data or resources directly with each other without a centralized server.
    
-   **Master-Introducer**: Some systems may elect a "master" node to coordinate requests and data sharing, especially in the case of system failures.
    
-   **Example**: File-sharing systems like BitTorrent or blockchain-based networks are prime examples of peer-to-peer architectures.
    

---

### **Software Architecture Patterns**:

Software architecture patterns provide reusable solutions to common problems faced during the design and development of software systems. These patterns guide the organization and structuring of applications to ensure scalability, maintainability, and efficiency.

#### Common Architecture Patterns:

1.  **MVC (Model-View-Controller)**:
    
    -   **Model**: Represents the core data and business logic of the application. This includes data structures, database access, and any business rules.
        
    -   **View**: The user interface (UI) of the application. It displays the data from the model and sends user commands to the controller.
        
    -   **Controller**: Acts as the intermediary between the model and view. It receives user input from the view, processes it (usually by updating the model), and then updates the view.
        
    
    **Example**: A basic web application where the model holds data about blog posts, the view displays the posts, and the controller handles user actions like adding or deleting posts.
    
2.  **MVP (Model-View-Presenter)**:
    
    -   **Model**: Same as in MVC, it represents the core data and business logic.
        
    -   **View**: The user interface that displays the data.
        
    -   **Presenter**: This acts similarly to the controller but with an emphasis on handling user interactions, updating the view, and maintaining the state of the view. The presenter often has more control over the view than in MVC.
        
    
    **Example**: In a to-do list app, the presenter updates the UI when a user adds or removes a task, while the model stores the task data.
    
3.  **MVVM (Model-View-ViewModel)**:
    
    -   **Model**: The data layer, representing the state and business logic.
        
    -   **View**: The UI that is presented to the user.
        
    -   **ViewModel**: The intermediary between the model and view. It maintains the state of the UI and performs logic based on the user’s input. Unlike MVP, the ViewModel may be tightly integrated with the view (through data-binding) in frameworks like Angular or React.
        
    
    **Example**: In a news app, the ViewModel holds the news articles and manages their updates, while the view simply renders the content.
    
4.  **HMVC (Hierarchical Model-View-Controller)**:
    
    -   An extension of MVC where each MVC triad can be nested within another MVC triad. This pattern is used to break down complex systems into smaller, more manageable sub-systems.
        
    -   **Example**: An e-commerce site could have separate MVC layers for different sections like the product catalog, shopping cart, and user profile.
        
5.  **.NET MVC and MVVM**:
    
    -   These architectures are commonly used in .NET web development. The approach emphasizes the separation of concerns and allows for better scalability, testing, and maintainability.
        
