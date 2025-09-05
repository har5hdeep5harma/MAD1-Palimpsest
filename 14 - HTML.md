# **What is HTML?**

-   **HTML (HyperText Markup Language)** is the standard language for creating web pages and web applications. It structures content on the web, including text, links, images, forms, and other multimedia elements.
    
-   **Markup Language:**
    
    -   A **markup language** is a set of rules that define how text and other content should be arranged and presented on a web page. Markup languages use tags to structure and define the meaning of content.
        
    -   **HTML** is a **descriptive markup language**, meaning that it defines the meaning or role of elements (such as headings, paragraphs, links, etc.) but does not dictate their visual style (this is handled by **CSS**).
        

#### **History of HTML:**

-   **Origins of HTML:**
    
    -   HTML was first developed by **Tim Berners-Lee** in 1989 while working at CERN (European Organization for Nuclear Research) as part of the creation of the World Wide Web.
        
    -   The early versions of HTML were based on **SGML (Standard Generalized Markup Language)**, a language designed to define the structure of documents.
        
-   **Evolution of HTML:**
    
    -   **HTML 2 (1995):** The first standardized version of HTML, which included basic features like text, images, tables, and links.
        
    -   **HTML 3 (1997):** Added support for more complex elements such as tables and forms.
        
    -   **HTML 4 (1997):** Introduced more sophisticated web features, including JavaScript, scripting, and more control over document structure.
        
    -   **XHTML (2000-2010):** XML-based version of HTML aimed to be stricter and more consistent.
        
    -   **HTML5 (2008-2014):** The current standard, which brought major updates such as native support for audio and video, local storage, and new semantic elements for better accessibility and search engine optimization (SEO).
        

#### **HTML Tags:**

HTML elements are defined using **tags**. Tags are keywords wrapped in angle brackets (`< >`). HTML uses two types of tags:

-   **Opening tags:** `<tagname>`
    
-   **Closing tags:** `</tagname>`
    

**Example:**

```html
<h1>Welcome to My Website</h1>
<p>This is a paragraph of text.</p>
```

Here, `<h1>` is an opening tag for a **heading**, and `</h1>` is the closing tag. Similarly, `<p>` denotes a paragraph, and `</p>` closes it.

#### **Key HTML Tags and Structure:**

Here’s a breakdown of essential HTML tags and their functions:

1.  **Document Structure Tags:**
    
    -   `<html>`: The root element that wraps the entire HTML document.
        
    -   `<head>`: Contains metadata (e.g., title, links to CSS, JavaScript files).
        
    -   `<title>`: Specifies the title of the web page (appears in the browser tab).
        
    -   `<body>`: Contains the content of the webpage that will be displayed to users.
        
    
    **Example:**
    
    ```html
    <html>
      <head>
        <title>My First Webpage</title>
      </head>
      <body>
        <h1>Welcome to My Website</h1>
        <p>This is a simple HTML page.</p>
      </body>
    </html>
    ```
    
2.  **Text Elements:**
    
    -   `<h1>`, `<h2>`, ..., `<h6>`: Heading tags, used to create headings. `<h1>` is the highest level, `<h6>` is the lowest.
        
    -   `<p>`: Paragraph tag, used to group blocks of text.
        
    -   `<a>`: Anchor tag, used to create hyperlinks. The `href` attribute defines the link's destination.
        
    -   `<ul>`, `<ol>`, `<li>`: Unordered (bulleted) and ordered (numbered) list tags. `<li>` defines list items.
        
    -   `<strong>`, `<em>`: Used for text emphasis. `<strong>` makes text bold, while `<em>` makes text italicized.
        
    
    **Example:**
    
    ```html
    <ul>
      <li>Apples</li>
      <li>Bananas</li>
    </ul>
    ```
    
3.  **Image and Multimedia:**
    
    -   `<img>`: The image tag. It requires a `src` (source) attribute to specify the image URL and an `alt` attribute for alternative text.
        
    -   `<audio>`: Embeds audio files.
        
    -   `<video>`: Embeds video files.
        
    
    **Example:**
    
    ```html
    <img src="image.jpg" alt="An image description">
    ```
    
4.  **Forms and Input:**
    
    -   `<form>`: Used to define a form.
        
    -   `<input>`: Defines an input field where users can enter data.
        
    -   `<button>`: Creates clickable buttons.
        
    
    **Example:**
    
    ```html
    <form>
      <label for="name">Name:</label>
      <input type="text" id="name" name="name">
      <button type="submit">Submit</button>
    </form>
    ```
    
5.  **Semantic HTML5 Elements:**
    
    -   **Semantic HTML** is the practice of using HTML elements that have meaningful names, making the content more understandable for both users and machines (e.g., search engines and screen readers).
        
    -   **New HTML5 elements** help define content more clearly:
        
        -   `<header>`: Represents a page header, typically containing a navigation menu or introductory content.
            
        -   `<footer>`: Represents the footer of a page, often containing copyright information or contact details.
            
        -   `<nav>`: Represents a navigation section.
            
        -   `<article>`: Represents a piece of self-contained content that could be distributed independently (e.g., blog post).
            
        -   `<section>`: Represents a section of content within a document.
            
    
    **Example:**
    
    ```html
    <header>
      <h1>My Website</h1>
      <nav>
        <ul>
          <li><a href="#home">Home</a></li>
          <li><a href="#about">About</a></li>
        </ul>
      </nav>
    </header>
    ```
    

#### **HTML Validation:**

-   **Valid HTML:** Ensures the document adheres to the correct syntax rules for tags, attributes, and nesting.
    
    -   Example of an invalid HTML tag:
        
        ```html
        <h1>Heading without closing tag
        ```
        
    -   A browser might still display the content, but the lack of a closing tag makes the document **invalid**.
        
-   **HTML Validators:** Tools like the **W3C HTML Validator** can help check if an HTML document adheres to the standards.
    

#### **Presentation vs. Semantics:**

-   **Presentation vs. Content:** HTML was initially used for both **structure (content)** and **style (presentation)**. However, with the rise of CSS, HTML is now primarily used for defining the structure of a document, while **CSS** handles the presentation (style).
    
    -   **Semantic HTML** focuses on meaning and structure, using appropriate tags to represent content logically. For instance:
        
        -   `<header>` for the header, `<footer>` for the footer, and `<article>` for an article.
            
    -   **Presentation Tags** like `<font>` and `<center>` were used for visual styles in older versions of HTML but are now deprecated in favor of CSS.
        

#### **Key Points about Markup Languages:**

1.  **HTML is a markup language** used to structure web content. It focuses on the meaning of the content rather than its visual appearance.
    
2.  **Tags define elements** within an HTML document, such as headings, paragraphs, links, and images.
    
3.  **HTML5 introduced semantic elements** like `<article>`, `<nav>`, and `<section>`, making it easier to understand and manipulate the content.
    
4.  **HTML is the backbone** of web content, with CSS and JavaScript providing styling and interactivity, respectively.
    
