# Java Programming - Class 2: Complete Lecture Notes
## Data Types, Variables and Literals

---

## 📚 Table of Contents

1. [Primitive Data Types Overview](#primitive-data-types-overview)
2. [Wrapper Classes](#wrapper-classes)
3. [Variable Declaration and Initialization](#variable-declaration-and-initialization)
4. [Variable, Classes, Object Naming Conventions](#variable-classes-object-naming-conventions)
5. [Number Systems in Java](#number-systems-in-java)
6. [Using Underscores in Numeric Literals](#using-underscores-in-numeric-literals)
7. [Number System Conversions](#number-system-conversions)
8. [Mantissa and Exponent (IEEE 754)](#mantissa-and-exponent-ieee-754)
9. [ASCII Codes](#ascii-codes)
10. [Literals](#literals)
11. [Type Casting](#type-casting)
12. [Constants](#constants)
13. [Practical Implementation](#practical-implementation)
14. [Complete Code Example](#complete-code-example)
15. [Key Takeaways](#key-takeaways)

---

## 🗃️ Primitive Data Types Overview

### Data Type Reference Table

| Type    | Size (bytes) | Range                                        | Default Value |
|---------|--------------|----------------------------------------------|---------------|
| `byte`  | 1            | -128 to 127                                 | 0             |
| `short` | 2            | -32,768 to 32,767                           | 0             |
| `int`   | 4            | -2,147,483,648 to 2,147,483,647             | 0             |
| `long`  | 8            | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 | 0L |
| `float` | 4            | 1.4e-45 to 3.4e38                           | 0.0f          |
| `double`| 8            | 4.9e-324 to 1.8e308                         | 0.0d          |
| `char`  | 2            | 0 to 65,535                                 | '\u0000'      |
| `boolean`| 1           | true or false                                | false         |

### Memory Categories

```
Java Data Types
├── Primitive Types (stored in stack)
│   ├── Numeric Types
│   │   ├── Integer Types (byte, short, int, long)
│   │   └── Floating Types (float, double)
│   ├── Character Type (char)
│   └── Boolean Type (boolean)
└── Reference Types (stored in heap)
    ├── Classes
    ├── Interfaces
    └── Arrays
```

---

## 📦 Wrapper Classes

### Object Representations of Primitive Data Types

Wrapper classes provide object representations of primitive data types, enabling them to be used in object-oriented contexts.

| Primitive Type | Wrapper Class |
|----------------|---------------|
| `byte`         | `Byte`        |
| `short`        | `Short`       |
| `int`          | `Integer`     |
| `long`         | `Long`        |
| `float`        | `Float`       |
| `double`       | `Double`      |
| `char`         | `Character`   |
| `boolean`      | `Boolean`     |

### Key Features of Wrapper Classes

- ✅ **Immutable**: Values cannot be changed after creation
- ✅ **Utility Methods**: Provide type conversion methods
- ✅ **Collection Compatible**: Required for ArrayList, HashMap, etc.
- ✅ **Autoboxing/Unboxing**: Automatic conversion support

### Finding Data Type Ranges

```java
// Using wrapper class constants
System.out.println("Integer range: " + Integer.MIN_VALUE + " to " + Integer.MAX_VALUE);
System.out.println("Double range: " + Double.MIN_VALUE + " to " + Double.MAX_VALUE);
System.out.println("Character range: " + (int)Character.MIN_VALUE + " to " + (int)Character.MAX_VALUE);
```

### Autoboxing and Unboxing

```java
// Autoboxing: primitive → wrapper object
int primitive = 10;
Integer wrapper = primitive;        // Automatic conversion

// Unboxing: wrapper object → primitive
Integer wrapperObj = new Integer(20);
int primitiveValue = wrapperObj;    // Automatic conversion
```

---

## 🔧 Variable Declaration and Initialization

### Variable Declaration

**Definition**: Creating a variable by specifying its data type and name.

```java
// Syntax: dataType variableName;
int age;
double salary;
String name;
boolean isActive;
```

### Variable Initialization

**Definition**: Assigning a value to a declared variable.

```java
age = 25;
salary = 50000.0;
name = "John Doe";
isActive = true;
```

### Combined Declaration and Initialization

```java
int age = 25;
double salary = 50000.0;
String name = "John Doe";
boolean isActive = true;
```

### Rules for Variable Declaration

- ✅ **Must start with**: letter, underscore (_), or dollar sign ($)
- ❌ **Cannot start with**: digit
- ❌ **Cannot use**: Java keywords (int, class, public, etc.)
- ⚠️ **Case-sensitive**: `age` and `Age` are different variables

### Variable Scope Types

| Scope Type | Location | Lifetime | Access |
|------------|----------|----------|---------|
| **Local** | Inside methods/blocks | Method execution | Local only |
| **Instance** | Class level (non-static) | Object lifetime | Through object |
| **Static** | Class level (static) | Program lifetime | Through class |

---

## 📝 Variable, Classes, Object Naming Conventions

### Variables and Methods

```java
// Use camelCase, start with lowercase
int studentAge;
String firstName;
double calculateTotalAmount();
boolean isValidUser();
```

### Classes and Interfaces

```java
// Use PascalCase (UpperCamelCase)
public class Student { }
public class BankAccount { }
public interface DatabaseConnection { }
```

### Constants

```java
// Use UPPER_CASE with underscores
public static final int MAX_SIZE = 100;
public static final double PI = 3.14159;
public static final String DEFAULT_NAME = "Unknown";
```

### Packages

```java
// Use lowercase with dots
package com.company.project;
package java.util;
package org.springframework.boot;
```

### Best Practices

- ✅ Use meaningful and descriptive names
- ✅ Avoid abbreviations unless widely understood
- ✅ Keep names concise but clear
- ✅ Use verbs for methods (`getName()`, `setAge()`)
- ✅ Use nouns for variables and classes

---

## 🔢 Number Systems in Java

Java supports four different number systems for representing integer values:

### Decimal (Base 10)
```java
// Digits: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9
int decimal = 255;
byte b = 123;
```

### Binary (Base 2)
```java
// Digits: 0, 1 | Prefix: 0b or 0B
int binary = 0b11111111;    // Represents 255 in decimal
byte binaryByte = 0B1010;   // Represents 10 in decimal
```

### Octal (Base 8)
```java
// Digits: 0, 1, 2, 3, 4, 5, 6, 7 | Prefix: 0
int octal = 0377;           // Represents 255 in decimal
int octalNum = 0123;        // Represents 83 in decimal
```

### Hexadecimal (Base 16)
```java
// Digits: 0-9, A-F | Prefix: 0x or 0X
int hex = 0xFF;             // Represents 255 in decimal
int hexNum = 0x7B;          // Represents 123 in decimal
```

### Number System Comparison

| Decimal | Binary     | Octal | Hexadecimal |
|---------|------------|-------|-------------|
| 10      | 1010       | 12    | A           |
| 15      | 1111       | 17    | F           |
| 255     | 11111111   | 377   | FF          |

### Practical Usage

- **Decimal**: Most common, everyday calculations
- **Binary**: Low-level programming, bit operations
- **Octal**: File permissions in Unix/Linux systems
- **Hexadecimal**: Memory addresses, color codes, debugging

---

## 🔍 Using Underscores in Numeric Literals

### Java 7+ Feature for Improved Readability

```java
// Valid usage examples
int million = 1_000_000;                    // Decimal
long creditCard = 1234_5678_9012_3456L;     // Long number
int binary = 0b1010_0001_1000_0101;         // Binary
int hex = 0xFF_EC_DE_5E;                    // Hexadecimal
float pi = 3.14_15_92F;                     // Float
double bigDecimal = 123_456.789_012;        // Double
```

### Rules for Underscore Usage

#### ✅ **ALLOWED**
- Between digits in any numeric literal
- In any number system (decimal, binary, octal, hexadecimal)
- Multiple underscores between digits
- In floating-point numbers

#### ❌ **NOT ALLOWED**
```java
int wrong1 = _1000;          // Error: at beginning
int wrong2 = 1000_;          // Error: at end
float wrong3 = 3._14F;       // Error: before decimal point
float wrong4 = 3.14_F;       // Error: before suffix
int wrong5 = 0_x52;          // Error: before 'x'
long wrong6 = 123_L;         // Error: before suffix
```

### Benefits

- ✅ Improves code readability
- ✅ Makes large numbers easier to understand
- ✅ Reduces counting errors
- ✅ Groups digits logically (thousands, credit card format)

---

## 🔄 Number System Conversions

### Manual Conversion Methods

#### Decimal to Binary
```
Method: Divide by 2 repeatedly, read remainders bottom-up
Example: Convert 13 to binary
13 ÷ 2 = 6 remainder 1
6 ÷ 2 = 3 remainder 0
3 ÷ 2 = 1 remainder 1
1 ÷ 2 = 0 remainder 1
Result: 1101
```

#### Binary to Decimal
```
Method: Multiply each digit by powers of 2
Example: Convert 1101 to decimal
1×2³ + 1×2² + 0×2¹ + 1×2⁰ = 8 + 4 + 0 + 1 = 13
```

### Java Built-in Conversion Methods

```java
// Converting FROM decimal
String binary = Integer.toBinaryString(10);     // Returns "1010"
String octal = Integer.toOctalString(10);       // Returns "12"
String hex = Integer.toHexString(10);           // Returns "a"

// Converting TO decimal
int fromBinary = Integer.parseInt("1010", 2);   // Binary to decimal = 10
int fromOctal = Integer.parseInt("12", 8);      // Octal to decimal = 10
int fromHex = Integer.parseInt("a", 16);        // Hex to decimal = 10
```

---

## ⚖️ Mantissa and Exponent (IEEE 754)

### IEEE 754 Standard Structure

#### Float (32-bit)
- **Sign bit**: 1 bit (0 = positive, 1 = negative)
- **Exponent**: 8 bits (bias = 127)
- **Mantissa**: 23 bits (significand)

#### Double (64-bit)
- **Sign bit**: 1 bit (0 = positive, 1 = negative)
- **Exponent**: 11 bits (bias = 1023)
- **Mantissa**: 52 bits (significand)

### Precision Guidelines

| Type | Reliable Decimal Digits | Example |
|------|-------------------------|---------|
| `float` | 6-7 digits | `1.2345679f` |
| `double` | 14-15 digits | `1.2345678901234567` |

### Special Values

```java
// Special floating-point values
float positiveInf = Float.POSITIVE_INFINITY;
float negativeInf = Float.NEGATIVE_INFINITY;
float notANumber = Float.NaN;

// Examples that produce special values
float result1 = 1.0f / 0.0f;     // Positive infinity
double result2 = -1.0 / 0.0;     // Negative infinity
double result3 = 0.0 / 0.0;      // NaN (Not a Number)
```

### Scientific Notation

```java
float scientific = 1.23e4f;      // 1.23 × 10⁴ = 12300.0
double avogadro = 6.022e23;      // Avogadro's number
double electron = 1.6e-19;       // Electronic charge
```

---

## 🔤 ASCII Codes

### ASCII Overview

ASCII (American Standard Code for Information Interchange) uses 7 bits to represent characters (0-127).

### Important ASCII Ranges

| Range | Characters | Description |
|-------|------------|-------------|
| 0-31 | Control chars | Non-printable (newline, tab, etc.) |
| 32 | Space | Space character |
| 48-57 | '0'-'9' | Digits |
| 65-90 | 'A'-'Z' | Uppercase letters |
| 97-122 | 'a'-'z' | Lowercase letters |

### Character to ASCII Conversion

```java
char c = 'A';
int ascii = (int) c;              // Returns 65
char backToChar = (char) ascii;   // Returns 'A'

// Useful conversions
char upper = 'A';
char lower = (char)(upper + 32);  // 'A' → 'a' (65 + 32 = 97)

char digit = '5';
int number = digit - '0';         // '5' → 5 (53 - 48 = 5)
```

---

## 📄 Literals

### Definition
Literals are fixed values that appear directly in the source code.

### Types of Literals

#### Integer Literals
```java
int decimal = 123;              // Decimal
int binary = 0b1010;           // Binary (prefix 0b)
int octal = 0123;              // Octal (prefix 0)
int hex = 0x7B;                // Hexadecimal (prefix 0x)
long longNum = 123L;           // Long (suffix L)
```

#### Floating-point Literals
```java
double defaultDouble = 3.14;   // Double (default for decimals)
double scientific = 2.5e10;    // Scientific notation
float floatNum = 3.14f;        // Float (suffix f or F)
```

#### Character Literals
```java
char letter = 'A';             // Single character
char newline = '\n';           // Escape sequence
char unicode = '\u0041';       // Unicode (represents 'A')
```

#### String Literals
```java
String message = "Hello World";
String multiLine = "Line 1\nLine 2";  // With escape sequences
```

#### Boolean Literals
```java
boolean isTrue = true;
boolean isFalse = false;
```

---

## 🔀 Type Casting

### Implicit Casting (Widening)

**Automatic conversion from smaller to larger data types**

```java
// Casting order: byte → short → int → long → float → double
byte b = 10;
short s = b;        // byte to short (automatic)
int i = s;          // short to int (automatic)
long l = i;         // int to long (automatic)
float f = l;        // long to float (automatic)
double d = f;       // float to double (automatic)

// Character to int
char c = 'A';
int ascii = c;      // char to int (automatic)
```

### Explicit Casting (Narrowing)

**Manual conversion from larger to smaller data types**

```java
// May cause data loss - must be explicit
double d = 9.78;
int i = (int)d;           // i = 9 (decimal part lost)

long l = 1234567890L;
int reducedInt = (int)l;  // May lose data if value too large

float f = 3.14159f;
int truncated = (int)f;   // truncated = 3
```

---

## 🔒 Constants

### Using the `final` Keyword

```java
// Instance constants
final int MAX_STUDENTS = 50;
final double PI = 3.14159;

// Class constants (static final)
public static final String COMPANY_NAME = "TechCorp";
public static final int MAX_RETRY_ATTEMPTS = 3;
public static final double GRAVITY = 9.81;
```

### Characteristics

- ✅ Must be initialized when declared or in constructor
- ✅ Values cannot be changed after initialization
- ✅ Convention: Use UPPER_CASE with underscores
- ✅ Can be declared at instance or class level

---

## 💻 Practical Implementation

### Program Objectives

Our example program demonstrates:

1. ✅ **Data type ranges and sizes using wrapper classes**
2. ✅ **Unicode character display**
3. ✅ **Variable initialization importance**
4. ✅ **Practical usage of different data types**

### Key Concepts Demonstrated

- **Wrapper class constants** for finding min/max values
- **Size information** in bits and bytes
- **Unicode character handling**
- **Compilation error** with uninitialized variables

---

## 📋 Complete Code Example

```java
public class DataTypesDemo {
    public static void main(String[] args) {
        
        // Integer type information
        System.out.println("=== INTEGER TYPES ===");
        System.out.println("Byte range: " + Byte.MIN_VALUE + " to " + Byte.MAX_VALUE);
        System.out.println("Byte size: " + Byte.SIZE + " bits, " + Byte.BYTES + " bytes");
        
        System.out.println("Short range: " + Short.MIN_VALUE + " to " + Short.MAX_VALUE);
        System.out.println("Short size: " + Short.SIZE + " bits, " + Short.BYTES + " bytes");
        
        System.out.println("Integer range: " + Integer.MIN_VALUE + " to " + Integer.MAX_VALUE);
        System.out.println("Integer size: " + Integer.SIZE + " bits, " + Integer.BYTES + " bytes");
        
        System.out.println("Long range: " + Long.MIN_VALUE + " to " + Long.MAX_VALUE);
        System.out.println("Long size: " + Long.SIZE + " bits, " + Long.BYTES + " bytes");
        
        // Floating-point type information
        System.out.println("\n=== FLOATING-POINT TYPES ===");
        System.out.println("Float range: " + Float.MIN_VALUE + " to " + Float.MAX_VALUE);
        System.out.println("Float size: " + Float.SIZE + " bits, " + Float.BYTES + " bytes");
        
        System.out.println("Double range: " + Double.MIN_VALUE + " to " + Double.MAX_VALUE);
        System.out.println("Double size: " + Double.SIZE + " bits, " + Double.BYTES + " bytes");
        
        // Character type information
        System.out.println("\n=== CHARACTER TYPE ===");
        System.out.println("Character range: " + (int)Character.MIN_VALUE + " to " + (int)Character.MAX_VALUE);
        System.out.println("Character size: " + Character.SIZE + " bits, " + Character.BYTES + " bytes");
        
        // Boolean type information
        System.out.println("\n=== BOOLEAN TYPE ===");
        System.out.println("Boolean values: " + Boolean.TRUE + ", " + Boolean.FALSE);
        
        // Unicode character demonstration
        System.out.println("\n=== UNICODE CHARACTERS ===");
        char heart = '\u2665';
        char spade = '\u2660';
        char diamond = '\u2666';
        char club = '\u2663';
        System.out.println("Card suits: " + heart + " " + spade + " " + diamond + " " + club);
        
        // Number system examples
        System.out.println("\n=== NUMBER SYSTEMS ===");
        int decimal = 255;
        int binary = 0b11111111;
        int octal = 0377;
        int hex = 0xFF;
        System.out.println("Decimal: " + decimal);
        System.out.println("Binary: " + binary + " (same as " + decimal + ")");
        System.out.println("Octal: " + octal + " (same as " + decimal + ")");
        System.out.println("Hex: " + hex + " (same as " + decimal + ")");
        
        // Underscore usage in large numbers
        System.out.println("\n=== UNDERSCORE USAGE ===");
        int million = 1_000_000;
        long creditCard = 1234_5678_9012_3456L;
        double pi = 3.14_15_92;
        System.out.println("One million: " + million);
        System.out.println("Credit card: " + creditCard);
        System.out.println("Pi: " + pi);
        
        // Type casting examples
        System.out.println("\n=== TYPE CASTING ===");
        
        // Implicit casting
        byte b = 10;
        int i = b;  // Automatic widening
        System.out.println("Implicit cast byte to int: " + b + " → " + i);
        
        // Explicit casting
        double d = 9.78;
        int truncated = (int)d;  // Manual narrowing
        System.out.println("Explicit cast double to int: " + d + " → " + truncated);
        
        // Constants demonstration
        System.out.println("\n=== CONSTANTS ===");
        final double PI = 3.14159;
        final int MAX_SIZE = 100;
        System.out.println("Pi constant: " + PI);
        System.out.println("Max size constant: " + MAX_SIZE);
        
        // Note: This would cause a compile error if uncommented
        // byte uninitialized;
        // System.out.println(uninitialized);  // Error: variable not initialized
    }
}
```

---

## 🎯 Key Takeaways

### Essential Concepts Mastered

1. **🗃️ Data Types**
   - 8 primitive data types with their ranges and sizes
   - Memory allocation differences (stack vs heap)
   - Default values for each type

2. **📦 Wrapper Classes**
   - Object representations of primitives
   - Autoboxing and unboxing mechanisms
   - Utility methods for type operations

3. **🔧 Variables**
   - Declaration, initialization, and scope
   - Naming conventions for professional code
   - Best practices for readable code

4. **🔢 Number Systems**
   - Decimal, binary, octal, and hexadecimal representations
   - Practical usage scenarios
   - Conversion methods (manual and programmatic)

5. **🔄 Type Casting**
   - Implicit (widening) vs explicit (narrowing) casting
   - Data loss prevention strategies
   - Safe casting practices

6. **📄 Literals**
   - Different types of literals in Java
   - Proper syntax and usage
   - Unicode character handling

### Best Practices Learned

- ✅ Always initialize variables before use
- ✅ Use meaningful and descriptive names
- ✅ Follow Java naming conventions consistently
- ✅ Use appropriate data types for memory efficiency
- ✅ Handle type casting carefully to avoid data loss
- ✅ Use constants for fixed values
- ✅ Leverage wrapper classes for object-oriented operations

### Common Pitfalls to Avoid

- ❌ Using uninitialized variables
- ❌ Ignoring data loss in explicit casting
- ❌ Using float for precise calculations (use BigDecimal)
- ❌ Confusing assignment (=) with comparison (==)
- ❌ Not handling integer division truncation

---

**🎓 You have successfully completed Java Programming Class 2!**

*Next class preview: Control Structures and Decision Making*
