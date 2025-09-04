# **ASCII (American Standard Code for Information Interchange):**

-   **What is ASCII?**
    
    -   **ASCII** is a character encoding standard that uses **7 bits** to represent text and control characters. Initially developed in the 1960s, it was designed to represent characters from the English alphabet, numbers, and a small set of special characters.
        
-   **How ASCII Works:**
    
    -   ASCII uses a total of **128** different combinations of 7 bits. Each combination corresponds to a unique character or control code.
        
    -   For example:
        
        -   The ASCII value for `A` is `65` in decimal, which corresponds to `01000001` in binary.
            
        -   The ASCII value for `a` is `97` in decimal, which corresponds to `01100001` in binary.
            
        -   Special characters like space (`32`), exclamation mark (`33`), and new line (`10`) also have specific ASCII codes.
            
-   **ASCII Table (Partial):**
    
    -   **Control Characters:** These include characters like new lines and carriage returns that manage text formatting and cursor movement.
        
        -   `NULL = 0`
            
        -   `LF (Line Feed) = 10`
            
        -   `CR (Carriage Return) = 13`
            
    -   **Printable Characters:** This includes all the visible characters.
        
        -   `A = 65`
            
        -   `a = 97`
            
        -   `1 = 49`
            
        -   `! = 33`
            
        -   `Space = 32`
            

#### **Limitations of ASCII:**

-   ASCII is limited to **128 characters**, which is insufficient for representing languages other than English or special characters from non-English alphabets (e.g., `अ`, `汉`).
    
-   **Non-Latin alphabets** like Arabic, Hebrew, or Chinese characters, and even emojis, are not part of ASCII. This is where **Unicode** comes into play.
    

#### **Unicode:**

-   **What is Unicode?**
    
    -   **Unicode** is an **international standard** designed to represent the text of every writing system, as well as symbols and emojis. It was created to overcome the limitations of ASCII and can represent **over 4 billion characters**.
        
    -   Unicode ensures that text can be correctly represented, regardless of language or platform.
        
-   **Unicode Encoding:**
    
    -   Unicode assigns a **unique number (code point)** to every character, whether it's an English letter, a Chinese symbol, or an emoji.
        
    -   These code points can be represented using different encoding schemes, such as **UTF-8**, **UTF-16**, and **UTF-32**.
        
-   **UCS (Universal Character Set):**
    
    -   The **UCS** is a subset of Unicode that includes all the characters and symbols that Unicode supports.
        
    -   UCS-2 uses **2 bytes per character**, allowing for 65,536 characters.
        
    -   UCS-4 uses **4 bytes per character**, allowing for over 4 billion characters.
        

#### **UTF-8:**

-   **What is UTF-8?**
    
    -   **UTF-8** is one of the most common encodings for Unicode and is used extensively on the web. It is a **variable-length encoding** that can represent each character with 1 to 4 bytes.
        
    -   The beauty of UTF-8 lies in its ability to be **backward compatible** with ASCII. The first 128 characters (which correspond to ASCII characters) are stored using 1 byte, making it efficient for English text.
        
-   **How UTF-8 Works:**
    
    -   **1 byte** for characters in the ASCII range (`0`–`127`), such as `A`, `B`, `1`, `@`.
        
    -   **2 bytes** for characters from extended Latin and some other languages (e.g., `é`, `ç`).
        
    -   **3 bytes** for most common characters from world languages (e.g., Greek, Cyrillic, and most non-Latin scripts).
        
    -   **4 bytes** for rare characters like emoji, ancient scripts, or mathematical symbols.
        
-   **UTF-8 Example:**
    
    -   The character `'A'` (ASCII `65`) is encoded as `01000001` in **UTF-8**.
        
    -   The character `'你'` (Chinese) is encoded as `11100101 10100101 10111101`, which uses **3 bytes** in **UTF-8**.
        
-   **Advantages of UTF-8:**
    
    -   **Space-efficient** for English and other languages that use ASCII.
        
    -   **Compatible with ASCII**, so legacy systems that use ASCII can still work with UTF-8.
        
    -   **Universal support**, meaning it's used by nearly all modern web applications and systems.
        
-   **Example of UTF-8 Encoding:**
    
    -   The word "hello" in UTF-8:
        
        -   `h = 01101000`
            
        -   `e = 01100101`
            
        -   `l = 01101100`
            
        -   `l = 01101100`
            
        -   `o = 01101111`
            
    -   These characters are all represented with 1 byte each in UTF-8, making the total size of the word "hello" in UTF-8 just **5 bytes**.
        

#### **Comparison:**

-   **ASCII vs. Unicode:**
    
    -   **ASCII**: Limited to 128 characters (1 byte per character).
        
    -   **Unicode**: Supports millions of characters and can represent any character or symbol in the world, using 1 to 4 bytes (depending on the encoding).
        
-   **UTF-8 vs. Other Unicode Encodings (UTF-16, UTF-32):**
    
    -   **UTF-8** is the most efficient and flexible encoding for most web applications since it uses fewer bytes for ASCII characters and can handle all Unicode characters.
        
    -   **UTF-16** uses 2 bytes for most characters but requires 4 bytes for some. It’s used primarily in environments that need to process a lot of non-ASCII characters (like in some programming languages or internal systems).
        
    -   **UTF-32** uses 4 bytes for every character, which is more memory-intensive but simple to work with since each character is the same size.
        

### **Key Takeaways:**

1.  **ASCII** is the original standard for encoding text, limited to 128 characters.
    
2.  **Unicode** is a universal standard designed to handle all written languages and characters.
    
3.  **UTF-8** is the most popular and efficient encoding for Unicode, particularly for web-based content. It’s backward-compatible with ASCII, making it widely adopted.
