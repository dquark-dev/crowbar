## Variables

In this way, a name can only be given to a memory location. It can be assigned values in two ways: 

1. Variable Initialization
2. Assigning value by taking input

**Types of Java Variables**
Now let us discuss different types of variables  which are listed as follows: 
1. Local Variables
2. Instance Variables
3. Static Variables

**Instance Variables vs Static Variables**
Now let us discuss the differences between the Instance variables and the Static variables:

- Each object will have its own copy of an instance variable, whereas we can only have one copy of a static variable per class, irrespective of how many objects we create. Thus, static variables are good for memory management.
- Changes made in an instance variable using one object will not be reflected in other objects as each object has its own copy of the instance variable. In the case of a static variable, changes will be reflected in other objects as static variables are common to all objects of a class.
- We can access instance variables through object references, and static variables can be accessed directly using the class name.
- Instance variables are created when an object is created with the use of the keyword ‘new’ and destroyed when the object is destroyed. Static variables are created when the program starts and destroyed when the program stops.

```
class GFG
{
    // Static variable
    static int a; 
    
    // Instance variable
    int b;        
} 
```

## Primitive Data Types

![[Pasted image 20250225183458.png]]

| Type    | Description             | Default | Size    | Example Literals                            | Range of values                                                       |
| ------- | ----------------------- | ------- | ------- | ------------------------------------------- | --------------------------------------------------------------------- |
| boolean | true or false           | false   | 8 bits  | true, false                                 | true, false                                                           |
| byte    | twos-complement integer | 0       | 8 bits  | (none)                                      | -128 to 127                                                           |
| char    | Unicode character       | \u0000  | 16 bits | ‘a’, ‘\u0041’, ‘\101’, ‘\\’, ‘\’, ‘\n’, ‘β’ | characters representation of ASCII values<br><br>0 to 255             |
| short   | twos-complement integer | 0       | 16 bits | (none)                                      | -32,768 to 32,767                                                     |
| int     | twos-complement intger  | 0       | 32 bits | -2,-1,0,1,2                                 | -2,147,483,648<br><br>to<br><br>2,147,483,647                         |
| long    | twos-complement integer | 0       | 64 bits | -2L,-1L,0L,1L,2L                            | -9,223,372,036,854,775,808<br><br>to<br><br>9,223,372,036,854,775,807 |
| float   | IEEE 754 floating point | 0.0     | 32 bits | 1.23e100f , -1.23e-100f , .3f ,3.14F        | upto 7 decimal digits                                                 |
| double  | IEEE 754 floating point | 0.0     | 64 bits | 1.23456e300d , -123456e-300d , 1e1d         | upto 16 decimal digits                                                |

```java
// Java Program to Demonstrate Char Primitive Data Type

class GFG 
{
    public static void main(String args[])
    {

        // Creating and initializing custom character
        char a = 'G';

        // Integer data type is generally
        // used for numeric values
        int i = 89;

        // use byte and short
        // if memory is a constraint
        byte b = 4;

        // this will give error as number is
        // larger than byte range
        // byte b1 = 7888888955;

        short s = 56;

        // this will give error as number is
        // larger than short range
        // short s1 = 87878787878;

        // by default fraction value
        // is double in java
        double d = 4.355453532;

        // for float use 'f' as suffix as standard
        float f = 4.7333434f;

        // need to hold big range of numbers then we need
        // this data type
        long l = 12121;

        System.out.println("char: " + a);
        System.out.println("integer: " + i);
        System.out.println("byte: " + b);
        System.out.println("short: " + s);
        System.out.println("float: " + f);
        System.out.println("double: " + d);
        System.out.println("long: " + l);
    }
}

```

## Non-Primitive (Reference) Data Types
The Non-Primitive (Reference) Data Types will contain a memory address of variable values because the reference types won’t store the variable value directly in memory. They are strings, objects, arrays, etc.

1. Strings
2. Class
3. Object
4. Interface
5. Array

for more
[Java Data Types - GeeksforGeeks](https://www.geeksforgeeks.org/data-types-in-java/?ref=lbp)

## Identifier

An identifier in Java is the name given to Variables, Classes, Methods, Packages, Interfaces, etc. These are the unique names and every Java Variables must be identified with unique names.

### **Rules For Naming Java Identifiers**

There are certain rules for defining a valid Java identifier. These rules must be followed, otherwise, we get a compile-time error. These rules are also valid for other languages like C, and C++. 

- The only allowed characters for identifiers are all alphanumeric characters, dollar sign and underscore. For example “geek@” is not a valid Java identifier as it contains a ‘@’ a special character.
- Identifiers should **not** start with digits. For example “123geeks” is not a valid Java identifier.
- Java identifiers are **case-sensitive**.
- There is no limit on the length of the identifier but it is advisable to use an optimum length of 4 – 15 letters only.
- **Reserved Words** can’t be used as an identifier. For example “int while = 20;” is an invalid statement as a while is a reserved word. There are ****53**** reserved words in Java.

### Reserved Words in Java
abstract	continue	for	protected	transient
Assert	Default	Goto	public	Try
Boolean	Do	If	Static	throws
break	double	implements	strictfp	Package
byte	else	import	super	Private
case	enum	Interface	Short	switch
Catch	Extends	instanceof	return	void
Char	Final	Int	synchronized	volatile
class	finally	long	throw	Date
const	float	Native	This	while

### Naming Conventions


## Input Functions

What are the different ways to take input in Java?
Methods to take input in Java as mentioned below:
- BufferedReader
- Scanner
- Console

### Scanner Class

```java
// packages
import java.util.Scanner;

// object construction
Scanner scn = new Scanner(System.in);

// variable declaration
int a = scn.nextInt();

// clearing resources
scn.close();

```

| Method                                                                                                   | Description                     |
| -------------------------------------------------------------------------------------------------------- | ------------------------------- |
| [****nextBoolean()****](https://www.geeksforgeeks.org/scanner-nextboolean-method-in-java-with-examples/) | Used for reading Boolean value. |
| [****nextByte()****](https://www.geeksforgeeks.org/scanner-nextbyte-method-in-java-with-examples/)       | Used for reading Byte value.    |
| [****nextDouble()****](https://www.geeksforgeeks.org/scanner-nextdouble-method-in-java-with-examples/)   | Used for reading Double value.  |
| [****nextFloat()****](https://www.geeksforgeeks.org/scanner-nextfloat-method-in-java-with-examples/)     | Used for reading Float value.   |
| [****nextInt()****](https://www.geeksforgeeks.org/scanner-nextint-method-in-java-with-examples/)         | Used for reading Int value.     |
| [****nextLine()****](https://www.geeksforgeeks.org/scanner-nextline-method-in-java-with-examples/)       | Used for reading Line value.    |
| [****nextLong()****](https://www.geeksforgeeks.org/scanner-nextlong-method-in-java-with-examples/)       | Used for reading Long value.    |
| [****nextShort()****](https://www.geeksforgeeks.org/scanner-nextshort-method-in-java-with-examples/)     | Used for reading Short value.   |

### Buffered Class

Constructors of BufferedReader Class

| Constructor                       | Action Performed                                                                            |
| --------------------------------- | ------------------------------------------------------------------------------------------- |
| BufferedReader(Reader in)         | Creates a buffering character-input stream that uses a default-sized input buffer           |
| BufferedReader(Reader in, int sz) | Creates a buffering character-input stream that uses an input buffer of the specified size. |

Methods of BufferedReader Class

| Method Name                                                                                                                                                                                                                                                         | Action                                                                                                                                                                                                                                                                                           |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [close()](https://www.geeksforgeeks.org/bufferedreader-close-method-in-java-with-examples/#:~:text=The%20close\(\)%20method%20of,associated%20with%20the%20stream%20operations.&text=Parameters%3A%20This%20method%20does%20not,does%20not%20return%20any%20value.) | Closes the stream and releases any system resources associated with it.Once the stream has been closed, further read(), ready(), mark(), reset(), or skip() invocations will throw an IOException. Closing a previously closed stream has no effect.                                             |
| [mark()](https://www.geeksforgeeks.org/bufferedreader-mark-method-in-java-with-examples/)                                                                                                                                                                           | Marks the present position in the stream. Subsequent calls to reset() will attempt to reposition the stream to this point.                                                                                                                                                                       |
| [markSupported()](https://www.geeksforgeeks.org/bufferedreader-marksupported-method-in-java-with-examples/)                                                                                                                                                         | Tells whether this stream supports the mark() operation, which it does.                                                                                                                                                                                                                          |
| [read()](https://www.geeksforgeeks.org/bufferedreader-read-method-in-java-with-examples/)                                                                                                                                                                           | Reads a single character.                                                                                                                                                                                                                                                                        |
| read (char[] cbuf, int off, int len)                                                                                                                                                                                                                                | Reads characters into a portion of an array. This method implements the general contract of the corresponding read method of the Reader class. As an additional convenience, it attempts to read as many characters as possible by repeatedly invoking the read method of the underlying stream. |
| [readLine()](https://www.geeksforgeeks.org/bufferedreader-readline-method-in-java-with-examples/)                                                                                                                                                                   | Reads a line of text. A line is considered to be terminated by any one of a line feed (‘\n’), a carriage return (‘\r’), or a carriage return followed immediately by a line feed.                                                                                                                |
| [ready()](https://www.geeksforgeeks.org/bufferedreader-ready-method-in-java-with-examples/)                                                                                                                                                                         | Tells whether this stream is ready to be read.                                                                                                                                                                                                                                                   |
| [reset()](https://www.geeksforgeeks.org/bufferedreader-reset-method-in-java-with-examples/)                                                                                                                                                                         | Resets the stream to the most recent mark.                                                                                                                                                                                                                                                       |
| [skip(long)](https://www.geeksforgeeks.org/bufferedreader-skiplong-method-in-java-with-examples/)                                                                                                                                                                   | Skips characters.                                                                                                                                                                                                                                                                                |

### BufferedReader vs Scanner Class

| Aspects                | BufferedReader                                   | Scanner                                                            |
| ---------------------- | ------------------------------------------------ | ------------------------------------------------------------------ |
| **Primary Use**        | Efficient reading of character streams.          | Reading formatted input (e.g., integers, strings).                 |
| **Speed**              | Faster for large input as it does less parsing.  | Slower due to parsing overhead (e.g., `nextInt()`, `nextFloat()`). |
| **Exception Handling** | Throws checked exceptions (e.g., `IOException`). | No checked exceptions; easier to use.                              |
| **Flexibility**        | Allows reading larger input efficiently.         | Best suited for reading simple data types.                         |
| **Thread Safety**      | Synchronized, making it thread-safe.             | Not thread-safe by default.                                        |
| **Common Use**         | Used for reading large input efficiently.        | Commonly used for smaller, formatted input.                        |
## 

