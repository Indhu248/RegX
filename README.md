# 📘 **Regular Expressions (RegEx) - Comprehensive Guide**

---

## **📚 Introduction**
Regular Expressions, commonly referred to as **RegEx**, are sequences of characters that define a **search pattern**. They are used to **match, extract, replace, and validate** text in many programming languages like **JavaScript, Python, Java, C#, and more**. 

With RegEx, you can easily perform complex string manipulations with just a few lines of code.

---

## **✨ Why Use RegEx?**
- **🔍 Pattern Matching**: Identify specific text patterns like emails, phone numbers, URLs, etc.
- **🛠️ Input Validation**: Validate user inputs (like email addresses, passwords, and usernames) in forms.
- **📄 Data Extraction**: Extract useful information from large datasets or log files.
- **✂️ Text Replacement**: Replace or remove specific parts of text (like extra whitespace or special characters).
- **📋 Data Scraping**: Extract information from HTML pages or web content.

---

## **📘 Basic Syntax and Patterns**
RegEx uses **special characters and symbols** to define patterns. Here are some of the most commonly used patterns in RegEx.

### **🛠️ Basic Special Characters**
| **Pattern**  | **Description**                | **Example**                 |
|--------------|--------------------------------|-----------------------------|
| `.`          | Matches **any character** except a newline | `h.t` matches "hat", "hit", "hot" |
| `^`          | Matches the **start** of a string  | `^Hello` matches "Hello world" but not "world Hello" |
| `$`          | Matches the **end** of a string    | `world$` matches "Hello world" but not "world Hello" |
| `*`          | Matches **0 or more repetitions** | `ab*` matches "a", "ab", "abb", "abbbb", etc. |
| `+`          | Matches **1 or more repetitions** | `ab+` matches "ab", "abb", "abbbb", but not "a" |
| `?`          | Matches **0 or 1 occurrence**     | `ab?` matches "a" or "ab" but not "abb" |
| `[]`         | Matches any **character inside the brackets** | `[a-z]` matches lowercase letters from a to z |
| `{n,m}`      | Matches **between n and m repetitions** | `\d{2,4}` matches 2 to 4 digit numbers like "12", "123", "4567" |
| `\d`         | Matches any **digit** (0-9)       | Matches "0", "1", "2", ..., "9" |
| `\w`         | Matches any **word character** (a-z, A-Z, 0-9, _) | Matches "hello123" but not "hello!" |
| `\s`         | Matches any **whitespace** character | Matches spaces, tabs, and newlines |
| `|`          | Matches **either or** (logical OR) | `cat|dog` matches "cat" or "dog" |

---

## **💻 Examples of RegEx Usage**
Here are some practical examples to understand how RegEx works.

### **1️⃣ Extract Email Addresses**
```javascript
const text = "Contact us at support@example.com or info@website.com";
const emails = text.match(/\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b/g);
console.log(emails); 
// Output: [ 'support@example.com', 'info@website.com' ]
```

### **2️⃣ Validate a Phone Number**
```javascript
const phoneNumber = "987-654-3210";
const isValid = /^\d{3}-\d{3}-\d{4}$/.test(phoneNumber);
console.log(isValid); 
// Output: true
```

### **3️⃣ Check for a Valid Password (8+ characters, at least 1 number, and 1 special character)**
```javascript
const password = "Pass@123";
const isValidPassword = /^(?=.*[A-Za-z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$/.test(password);
console.log(isValidPassword); 
// Output: true
```

### **4️⃣ Replace Multiple Spaces with a Single Space**
```javascript
const sentence = "This    is   a  test  string";
const result = sentence.replace(/\s+/g, ' ');
console.log(result); 
// Output: "This is a test string"
```

### **5️⃣ Extract All Numbers from a String**
```javascript
const text = "The price of item A is 100 and item B is 250";
const numbers = text.match(/\d+/g);
console.log(numbers); 
// Output: [ '100', '250' ]
```

---

## **🌐 Differences in RegEx Across Languages**
While the **core syntax of RegEx is similar across languages**, some details (like methods to call RegEx or supported features) may vary. Here's a comparison of how you can use RegEx in different languages.

| **Language**  | **RegEx Usage**                         | **Syntax Example**         |
|---------------|-----------------------------------------|----------------------------|
| **JavaScript**| `str.match(pattern)` or `pattern.test(str)` | `/\d+/g` to match digits    |
| **Python**    | `import re` → `re.findall(pattern, str)` | `\d+` matches numbers       |
| **Java**      | `Pattern.compile(pattern)` → `matcher.find()` | `\\d+` matches numbers      |
| **C#**        | `Regex.Match(input, pattern)`            | `\d+` matches numbers       |
| **PHP**       | `preg_match_all(pattern, string)`       | `/\d+/` matches numbers     |

---
# **🚀 Mastering RegEx in Different Programming Languages**

---

## **🛠️ RegEx in Different Languages (With Simple Examples)**

---

### **1️⃣ JavaScript**
#### **How to Use**
- **RegEx Syntax**: `/pattern/flags`  
- **Functions**: `match()`, `test()`, `replace()`, etc.  

#### **Example 1: Extract Emails**
```javascript
const text = "Contact me at indu@example.com and support@example.com";
const emails = text.match(/\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b/g);
console.log(emails); 
// Output: ['indu@example.com', 'support@example.com']
```

#### **Example 2: Validate Phone Numbers**
```javascript
const phoneNumber = "987-654-3210";
const isValid = /^\d{3}-\d{3}-\d{4}$/.test(phoneNumber);
console.log(isValid); 
// Output: true
```

---

### **2️⃣ Python**
#### **How to Use**
- **Import Module**: `import re`  
- **Functions**: `re.match()`, `re.findall()`, `re.sub()`, etc.  

#### **Example 1: Extract Emails**
```python
import re

text = "Send your emails to indu@example.com and info@website.com"
emails = re.findall(r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b', text)
print(emails) 
# Output: ['indu@example.com', 'info@website.com']
```

#### **Example 2: Validate Phone Numbers**
```python
import re

phone_number = "987-654-3210"
is_valid = bool(re.match(r'^\d{3}-\d{3}-\d{4}$', phone_number))
print(is_valid) 
# Output: True
```

---

### **3️⃣ Java**
#### **How to Use**
- **Import Module**: `import java.util.regex.*;`  
- **Functions**: `Pattern.compile()`, `matcher.find()`, etc.  

#### **Example 1: Extract Emails**
```java
import java.util.regex.*;

public class Main {
    public static void main(String[] args) {
        String text = "Please send an email to indu@example.com and info@website.com";
        Pattern pattern = Pattern.compile("\\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\\.[A-Z|a-z]{2,}\\b");
        Matcher matcher = pattern.matcher(text);
        
        while (matcher.find()) {
            System.out.println(matcher.group());
        }
    }
}
// Output: indu@example.com, info@website.com
```

#### **Example 2: Validate Phone Numbers**
```java
import java.util.regex.*;

public class Main {
    public static void main(String[] args) {
        String phoneNumber = "987-654-3210";
        boolean isValid = phoneNumber.matches("\\d{3}-\\d{3}-\\d{4}");
        System.out.println(isValid); 
        // Output: true
    }
}
```

---

### **4️⃣ C#**
#### **How to Use**
- **Import Module**: `using System.Text.RegularExpressions;`  
- **Functions**: `Regex.Match()`, `Regex.IsMatch()`, etc.  

#### **Example 1: Extract Emails**
```csharp
using System;
using System.Text.RegularExpressions;

class Program
{
    static void Main() 
    {
        string text = "Email us at indu@example.com and info@website.com";
        MatchCollection matches = Regex.Matches(text, @"\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b");

        foreach (Match match in matches) 
        {
            Console.WriteLine(match.Value);
        }
    }
}
// Output: indu@example.com, info@website.com
```

#### **Example 2: Validate Phone Numbers**
```csharp
using System;
using System.Text.RegularExpressions;

class Program
{
    static void Main() 
    {
        string phoneNumber = "987-654-3210";
        bool isValid = Regex.IsMatch(phoneNumber, @"^\d{3}-\d{3}-\d{4}$");
        Console.WriteLine(isValid); 
        // Output: true
    }
}
```

---

### **5️⃣ PHP**
#### **How to Use**
- **Functions**: `preg_match()`, `preg_match_all()`, `preg_replace()`, etc.  

#### **Example 1: Extract Emails**
```php
<?php
$text = "Please send an email to indu@example.com and info@website.com";
preg_match_all("/\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b/", $text, $matches);
print_r($matches[0]);
// Output: ['indu@example.com', 'info@website.com']
?>
```

#### **Example 2: Validate Phone Numbers**
```php
<?php
$phoneNumber = "987-654-3210";
$isValid = preg_match("/^\d{3}-\d{3}-\d{4}$/", $phoneNumber);
echo $isValid; 
// Output: 1 (true)
?>
```

---

## **🧠 How to Remember RegEx Easily**
Here’s a simple way to remember key RegEx concepts:  
1. **Break It Down**: Don't try to learn it all at once. Start with `\d` (digits), `\w` (words), and `\s` (spaces).  
2. **Visualize It**: Use tools like [regex101](https://regex101.com/) to visualize how patterns match text.  
3. **Practice**: Write simple patterns like matching numbers, emails, or phone numbers.  
4. **Create Your Cheat Sheet**: Write down patterns you use often and refer to them later.  
5. **Think of It as LEGO Blocks**: Combine pieces like `^`, `$`, `+`, and `\d` to build complex patterns.  

---

## **📦 Real-World Use Cases**
- **📧 Email Validation**: Ensuring user-provided emails follow a standard format.
- **🔒 Password Validation**: Ensuring a password contains at least one uppercase, lowercase, digit, and special character.
- **📄 Log File Analysis**: Extracting error codes, timestamps, and log messages from server logs.
- **🛍️ E-commerce**: Scraping product details (like prices, names) from HTML source code.

---

## **🧑‍💻 Tips & Tricks**
1. **Use Online Tools**: Websites like [regex101](https://regex101.com/) help visualize and test your RegEx patterns.
2. **Keep Patterns Simple**: Avoid overly complex patterns; break them down for better readability.
3. **Use Flags (Modifiers)**: Flags like `g` (global), `i` (case-insensitive) improve performance.
    - Example: `/hello/gi` matches "hello", "Hello", "HELLO" in the text.
4. **Escape Special Characters**: Use `\` to escape characters like `.`, `*`, `+`, `?`, `(`, and `)`.
    - Example: To match a literal `.` in a sentence, use `\.`.

---

## **🛠️ Flags in RegEx**
| **Flag** | **Description**                | **Example**                 |
|----------|---------------------------------|-----------------------------|
| `g`      | Global match (all occurrences) | `/abc/g` matches "abc" everywhere|
| `i`      | Case-insensitive matching     | `/abc/i` matches "ABC", "Abc" |
| `m`      | Multiline matching            | Affects `^` and `$` to match each line |
| `u`      | Unicode support               | Supports Unicode characters like emojis|
| `s`      | Dot (.) matches newline       | `/./s` matches any character including newlines|

---

## **📚 Resources**
- [Regex101](https://regex101.com/) — Test and visualize RegEx patterns.
- [MDN Regular Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) — Official documentation for RegEx in JavaScript.
- [Regex Cheatsheet](https://www.regular-expressions.info/quickstart.html) — A quick reference to RegEx patterns and syntax.

---

## **📄 License**
This project is licensed under the MIT License.

---

## **💬 Contributing**
Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

---

## **📞 Contact**
If you have any questions, feel free to reach out!  
**Author**: Indravathi Botcha
**GitHub**: [Your GitHub Profile](#)  

