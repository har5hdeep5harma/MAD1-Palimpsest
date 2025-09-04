# **Information Representation**

How information is represented in computers, focusing on bits, binary numbers, and text encoding.

#### **Binary Digits (Bits):**

-   **What are Bits?**
    
    -   A **bit** (short for **binary digit**) is the most basic unit of data in computing, representing either a `0` or a `1`. All digital information (text, images, audio, etc.) is eventually converted into bits so that computers can process them.
        
    -   Computers use the binary number system because it is simple to implement with electrical circuits that are either on (1) or off (0).
        
-   **Place Value in Binary:**
    
    -   Just like decimal (base-10) numbers, binary (base-2) numbers also have place values. However, instead of being based on powers of 10, the place values are based on powers of 2.
        
    -   **Example of Place Value in Binary:**
        
        -   Take the binary number `0110`. From right to left, the place values are powers of 2:
            
            -   $2^0 = 1$
                
            -   $2^1 = 2$
                
            -   $2^2 = 4$
                
            -   $2^3 = 8$
                
        -   To convert `0110` into decimal:
            
            -   $0 \times 8 + 1 \times 4 + 1 \times 2 + 0 \times 1 = 6$ in decimal.
                
        -   **Key Point:** Each place represents a power of 2. For example, `1101` would be $1 \times 8 + 1 \times 4 + 0 \times 2 + 1 \times 1 = 13$.
            

#### **Two's Complement:**

-   **What is Two's Complement?**
    
    -   The two's complement system is used for representing signed (positive and negative) integers in binary. This system allows us to represent negative numbers without needing a separate sign bit.
        
    -   **How to Convert a Positive Number to Negative (Two's Complement):**
        
        1.  **Invert the bits** of the positive number (change `0` to `1` and `1` to `0`).
            
        2.  **Add 1** to the inverted bits.
            
    -   **Example:**
        
        -   Let's convert `6` to binary and then find its two's complement:
            
            -   6 in binary is `0110`.
                
            -   Invert the bits: `1001`.
                
            -   Add 1: `1010`.
                
            -   So, the two's complement representation of `-6` in 4-bit binary is `1010`.
                
-   **Why Two's Complement is Useful:**
    
    -   Two's complement simplifies binary arithmetic (especially for addition and subtraction) because the same operation can be used for both positive and negative numbers.
        

### **Understanding Text Representation:**

#### **Representing Text with ASCII and Unicode**

-   **ASCII (American Standard Code for Information Interchange):**
    
    -   ASCII is a 7-bit encoding standard that represents **128** characters, including:
        
        -   English alphabet letters (both uppercase and lowercase).
            
        -   Numbers (`0` to `9`).
            
        -   Basic punctuation marks (like `!`, `@`, `#`).
            
        -   Control characters (like newline `\n`, carriage return `\r`).
            
    -   **Why 7 bits?**
        
        -   With 7 bits, we can represent 128 unique values, which was sufficient for the basic Latin alphabet and control characters at the time ASCII was created.
            
    -   **ASCII Table:**
        
        -   Here’s a quick reference for some common ASCII characters:
            
            -   `A = 65`, `B = 66`, ..., `Z = 90`
                
            -   `a = 97`, `b = 98`, ..., `z = 122`
                
            -   Numbers: `0 = 48`, `1 = 49`, ..., `9 = 57`
                
            -   Special characters: `! = 33`, `@ = 64`, `# = 35`, etc.
                

#### **Unicode:**

-   **What is Unicode?**
    
    -   Unicode is an extended standard for character encoding, designed to cover all written languages in the world (living and historical), including mathematical symbols, emojis, and scripts from ancient civilizations.
        
    -   Unlike ASCII, which was limited to 128 characters, Unicode can support over **4 billion** unique characters.
        
-   **UCS-2 and UCS-4:**
    
    -   **UCS-2:** Uses **2 bytes** per character, capable of encoding **65,536 characters**.
        
    -   **UCS-4:** Uses **4 bytes** per character, supporting **over 4 billion** unique characters.
        

#### **UTF-8 Encoding:**

-   **Why is UTF-8 important?**
    
    -   UTF-8 is a variable-length encoding that can represent all characters in the Unicode standard. It uses **1 to 4 bytes** to encode each character.
        
    -   It is **backward compatible with ASCII**, meaning that all ASCII characters are represented in the same way in UTF-8.
        
-   **How does UTF-8 work?**
    
    -   **1 byte**: For characters in the ASCII set (such as `A`, `b`, `1`, `!`).
        
    -   **2 bytes**: For characters like `é`, `©`, `ç`.
        
    -   **3 bytes**: For most common characters from various world languages.
        
    -   **4 bytes**: For less common characters like emoji or certain Asian characters.
        
    -   **Example of UTF-8 Encoding for 'A':**
        
        -   The character `'A'` is represented as `65` in ASCII, which is `01000001` in binary. This fits within 1 byte in UTF-8.
            
    -   **Example of UTF-8 Encoding for '好':**
        
        -   The Chinese character `'好'` uses **3 bytes** in UTF-8 and is represented as `E5 A5 BD` in hexadecimal.
            

#### **Efficiency in Encoding:**

-   **Why should all characters not use the same number of bits?**
    
    -   Different characters have varying frequency of use. For instance, the letter `'e'` is the most common letter in English and could be encoded more efficiently than rare symbols like `'ß'` or `'π'`.
        
    -   **Optimal Encoding:**
        
        -   You could use techniques like **Huffman coding**, which encodes more frequent characters with shorter bit patterns to reduce overall size. This is a form of **lossless data compression**.
