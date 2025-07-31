# Java Programming - Class 1: Complete Lecture Notes

---

## 📚 Table of Contents

1. [Java Development Environment](#java-development-environment)
2. [Java Program Structure](#java-program-structure)
3. [Scanner Class for User Input](#scanner-class-for-user-input)
4. [Practical Implementation](#practical-implementation)
5. [Complete Code Example](#complete-code-example)
6. [Scanner Methods Reference](#scanner-methods-reference)
7. [Key Takeaways](#key-takeaways)

---

## 🛠️ Java Development Environment

### Understanding Java Components

```
JDK (Java Development Kit)
├── Development Tools (javac, javap, etc.)
└── JRE (Java Runtime Environment)
    ├── Java Libraries
    └── JVM (Java Virtual Machine)
```

### Java Program Compilation & Execution Flow

```
Source Code → Compiler → Bytecode → JVM → Output
First.java → javac First.class → java First → Result
```

**Step-by-step process:**
1. **Write** Java source code in `.java` file
2. **Compile** using `javac` compiler to generate `.class` file (bytecode)
3. **Execute** using `java` command which runs the bytecode on JVM
4. **Output** is displayed to the user

---

## 🏗️ Java Program Structure

Every Java program follows a specific structure:

```java
// 1. Import statements (if needed)
import java.io.*;
import java.util.*;

// 2. Class declaration
public class ClassName {
    
    // 3. Main method - entry point of program
    public static void main(String args[]) {
        // Program logic goes here
    }
}
```

---

## 🔍 Scanner Class for User Input

The `Scanner` class is a powerful tool for reading user input from various sources, primarily the console.

### Why Use Scanner?

- **Versatile**: Can read different data types
- **User-friendly**: Easy to implement for interactive programs
- **Built-in**: Part of `java.util` package

### Setting Up Scanner

```java
import java.util.Scanner;  // Import Scanner class

Scanner sc = new Scanner(System.in);  // Create Scanner object
```

---

## 💻 Practical Implementation

### Program Objectives

Our example program demonstrates how to:

1. ✅ **Read two integers and calculate their sum**
2. ✅ **Handle mixed data types (integer + float)**
3. ✅ **Process single word strings**
4. ✅ **Handle multi-word strings with spaces**
5. ✅ **Create interactive user experience**

### Step-by-Step Implementation

#### Step 1: Basic Integer Operations
```java
System.out.println("Enter two integers to add:");
int a = sc.nextInt();
int b = sc.nextInt();
int c = a + b;
System.out.println("Sum is " + c);
```

#### Step 2: Mixed Data Types
```java
System.out.println("Enter an integer and a float:");
int x = sc.nextInt();
float y = sc.nextFloat();
System.out.println("Integer: " + x);
System.out.println("Float: " + y);
```

#### Step 3: String Input (Single Word)
```java
System.out.println("Enter a String:");
String str1 = sc.next(); // reads until whitespace
System.out.println("You entered: " + str1);
```

#### Step 4: String Input (Full Line)
```java
System.out.println("Enter a line with spaces:");
String str2 = sc.nextLine(); // reads entire line
System.out.println("Full line: " + str2);
```

#### Step 5: Interactive Greeting
```java
System.out.println("May I know your name?");
String name = sc.nextLine();
System.out.println("Welcome " + name + "!");
```

---

## 📋 Complete Code Example

```java
import java.io.*;
import java.util.*;

public class C01 {
    public static void main(String args[]) {
        
        // Initialize Scanner for user input
        Scanner sc = new Scanner(System.in);

        // 1. INTEGER ARITHMETIC
        System.out.println("=== INTEGER ADDITION ===");
        System.out.println("Enter two integers to add:");
        int a, b, c;
        
        a = sc.nextInt();
        b = sc.nextInt();
        c = a + b;
        
        System.out.println("Sum is " + c);
        System.out.println();

        // 2. MIXED DATA TYPES
        System.out.println("=== MIXED DATA TYPES ===");
        System.out.println("Enter an integer and a float:");
        int x = sc.nextInt();
        float y = sc.nextFloat();
        
        System.out.println("Integer entered: " + x);
        System.out.println("Float entered: " + y);
        System.out.println();

        // 3. SINGLE WORD STRING
        System.out.println("=== SINGLE WORD INPUT ===");
        System.out.println("Enter a String:");
        String str1 = sc.next(); // reads a single word
        System.out.println("Word entered: " + str1);
        System.out.println();

        // 4. FULL LINE STRING
        System.out.println("=== FULL LINE INPUT ===");
        System.out.println("Enter a line with spaces:");
        String str2 = sc.nextLine(); // reads a line with spaces
        System.out.println("Line entered: " + str2);
        System.out.println();

        // 5. INTERACTIVE GREETING
        System.out.println("=== PERSONAL GREETING ===");
        System.out.println("May I know your name?");
        String name = sc.nextLine();
        System.out.println("Welcome " + name + "!");
        
        // Good practice: Close Scanner (optional in simple programs)
        sc.close();
    }
}
```

---

## 📖 Scanner Methods Reference

### 🔢 Numeric Input Methods

| Method | Data Type | Description | Example |
|--------|-----------|-------------|---------|
| `nextByte()` | byte | Reads a byte value | `byte b = sc.nextByte();` |
| `nextShort()` | short | Reads a short integer | `short s = sc.nextShort();` |
| `nextInt()` | int | Reads an integer | `int i = sc.nextInt();` |
| `nextLong()` | long | Reads a long integer | `long l = sc.nextLong();` |
| `nextFloat()` | float | Reads a float value | `float f = sc.nextFloat();` |
| `nextDouble()` | double | Reads a double value | `double d = sc.nextDouble();` |

### 📝 String Input Methods

| Method | Description | Use Case |
|--------|-------------|----------|
| `next()` | Reads single word (stops at whitespace) | Names, single words |
| `nextLine()` | Reads entire line (including spaces) | Sentences, addresses |

### 🔍 Boolean Input Method

| Method | Description | Example |
|--------|-------------|---------|
| `nextBoolean()` | Reads boolean value (true/false) | `boolean flag = sc.nextBoolean();` |

### 🔍 BigInteger Input Method

| Method | Description | Use Case |
|--------|-------------|----------|
| `nextBigInteger()` | Reads very large integers | Mathematical calculations |

---

### 🛡️ Input Validation Methods

| Method | Description | Purpose |
|--------|-------------|---------|
| `hasNextInt()` | Checks if next input is integer | Prevent input errors |
| `hasNextFloat()` | Checks if next input is float | Validate numeric input |
| `hasNextDouble()` | Checks if next input is double | Type safety |
| `hasNext()` | Checks if there's another string | Stream validation |
| `hasNextLine()` | Checks if there's another line | Line availability |

### Example of Input Validation

```java
if (sc.hasNextInt()) {
    int number = sc.nextInt();
    System.out.println("Valid integer: " + number);
} else {
    System.out.println("Invalid input! Please enter an integer.");
}
```

---

## 🔧 Development Tools & Commands

### Useful Commands

| Command | Purpose | Example |
|---------|---------|---------|
| `javac FileName.java` | Compile Java source code | `javac C01.java` |
| `java ClassName` | Run compiled Java program | `java C01` |
| `javap ClassName` | Disassemble class file | `javap java.util.Scanner` |

### Using javap for Documentation

```bash
javap java.util.Scanner
```

This command shows the complete structure and methods of the Scanner class, helping you understand all available methods and their signatures.

---

## 🎯 Key Takeaways

### ✅ What We Learned

1. **Java Environment**: Understanding JDK, JRE, and JVM relationship
2. **Program Structure**: Basic Java program organization
3. **Scanner Class**: Comprehensive input handling
4. **Data Types**: Working with various primitive types
5. **String Handling**: Difference between `next()` and `nextLine()`
6. **Interactive Programming**: Creating user-friendly console applications

### 💡 Best Practices

1. **Always import** required classes at the top
2. **Use meaningful variable names** for better code readability
3. **Add comments** to explain complex logic
4. **Close Scanner objects** when done (good practice)
5. **Validate input** when necessary using `hasNext()` methods
6. **Handle exceptions** in production code

### ⚠️ Common Pitfalls

1. **Buffer Issues**: Be careful when mixing `nextLine()` with other methods
2. **Input Mismatch**: Ensure input type matches expected type
3. **Resource Management**: Close Scanner objects to free resources

### 🚀 Next Steps

- Practice with different data types
- Experiment with input validation
- Learn about exception handling for robust input processing
- Explore file input using Scanner

---

## 📝 Practice Exercises

1. **Calculator**: Create a program that performs all basic arithmetic operations
2. **Data Collection**: Build a program that collects student information (name, age, grade)
3. **Input Validation**: Implement a program that validates user input before processing
4. **Interactive Menu**: Create a simple menu-driven program using Scanner

---

*This completes our comprehensive coverage of Java basics and Scanner class usage. Practice these concepts to build a strong foundation for advanced Java programming.*

---

**Course:** Abdul Bari Sir - Java Programming  
**Class:** 1  
**Topic:** Java Basics 
