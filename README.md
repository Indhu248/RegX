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
**Author**: Indu  
**GitHub**: [Your GitHub Profile](#)  

---

This **README.md** file is ready to be uploaded to your GitHub repo. Let me know if you'd like any changes or additional sections. 🚀
