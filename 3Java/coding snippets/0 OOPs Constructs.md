## Basic Classes

```java
package day2;

public class Account {

	private int accno, balance;
	private String name;
	
	private static float intrate ;
	
	static
	{
		System.out.println("Block1");
		intrate =6.5f;
	}
	
	static
	{
		System.out.println("Block2");
	}
	
	public Account(int accno, String name, int balance)
	{
		this.accno = accno;
		this.name = name;
		this.balance = balance;
	}
	
	public void calculateInterest()
	{
		double interest = (balance * intrate*0.25)/100;
		System.out.println("Interest earned : " + interest);
	}
	
	public static void displayInterstRate()
	{
		System.out.println("Current Interest Rate : "+ intrate);
	}
}

```

## Access Specifiers
### public
- Accessibility: Accessible from anywhere (within the same class, same package, or other packages).
- Use Case: Used when you want to make a class, method, or field accessible globally.

```java
// Class is public, so it can be accessed from anywhere
public class MyClass {
    // Public field
    public int publicField = 10;

    // Public method
    public void publicMethod() {
        System.out.println("This is a public method.");
    }
}

// Accessing from another class in a different package
public class AnotherClass {
    public static void main(String[] args) {
        MyClass obj = new MyClass();
        System.out.println(obj.publicField); // Accessing public field
        obj.publicMethod(); // Accessing public method
    }
}
```

### private
- Accessibility: Accessible only within the same class.
- Use Case: Used to encapsulate and hide the internal details of a class. Prevents external access to sensitive data or methods.

```java
public class MyClass {
    // Private field
    private int privateField = 20;

    // Private method
    private void privateMethod() {
        System.out.println("This is a private method.");
    }

    // Public method to access private field and method
    public void accessPrivate() {
        System.out.println(privateField); // Accessing private field
        privateMethod(); // Accessing private method
    }
}

public class AnotherClass {
    public static void main(String[] args) {
        MyClass obj = new MyClass();
        // System.out.println(obj.privateField); // Error: privateField is not accessible
        // obj.privateMethod(); // Error: privateMethod is not accessible
        obj.accessPrivate(); // Accessing private members via a public method
    }
}
```

### protected
- Accessibility: Accessible within the same package and by subclasses (even if they are in different packages)
- Use Case: Used when you want to allow access to subclasses while restricting access from unrelated classes.

```java
// In package1
package package1;

public class ParentClass {
    // Protected field
    protected int protectedField = 30;

    // Protected method
    protected void protectedMethod() {
        System.out.println("This is a protected method.");
    }
}

// In package2
package package2;

import package1.ParentClass;

public class ChildClass extends ParentClass {
    public void accessProtected() {
        System.out.println(protectedField); // Accessing protected field
        protectedMethod(); // Accessing protected method
    }
}

public class AnotherClass {
    public static void main(String[] args) {
        ChildClass obj = new ChildClass();
        obj.accessProtected(); // Accessing protected members via subclass
    }
}
```

### default (Package-Private)
- Accessibility: Accessible only within the same package.
- Use Case: Used when you want to restrict access to classes within the same package.

```java
// In package1
package package1;

class DefaultClass {
    // Default field
    int defaultField = 40;

    // Default method
    void defaultMethod() {
        System.out.println("This is a default method.");
    }
}

public class AnotherClassInSamePackage {
    public static void main(String[] args) {
        DefaultClass obj = new DefaultClass();
        System.out.println(obj.defaultField); // Accessing default field
        obj.defaultMethod(); // Accessing default method
    }
}

// In package2
package package2;

import package1.DefaultClass;

public class AnotherClassInDifferentPackage {
    public static void main(String[] args) {
        // DefaultClass obj = new DefaultClass(); // Error: DefaultClass is not accessible
        // System.out.println(obj.defaultField); // Error: defaultField is not accessible
        // obj.defaultMethod(); // Error: defaultMethod is not accessible
    }
}
```

## inheritance + covariant return
```java
class Shape {
    public Shape createShape() {
        return new Shape();
    }
}

class Circle extends Shape {
    @Override
    public Circle createShape() {
        return new Circle();
    }
}

class Rectangle extends Shape {
    @Override
    public Rectangle createShape() {
        return new Rectangle();
    }
}
```

## interface

```java
// Define an interface
interface Animal {
    // Abstract method
    void makeSound();

    // Default method
    default void sleep() {
        System.out.println("Sleeping...");
    }

    // Static method
    static void info() {
        System.out.println("This is an Animal interface.");
    }
}

// Implement the interface
class Dog implements Animal {
    // Provide implementation for the abstract method
    public void makeSound() {
        System.out.println("Bark!");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.makeSound(); // Output: Bark!
        dog.sleep();     // Output: Sleeping...
        Animal.info();   // Output: This is an Animal interface.
    }
}
```

### multi interface inheritance

```java
interface Flyable {
    void fly();
}

interface Swimmable {
    void swim();
}

class Duck implements Flyable, Swimmable {
    public void fly() {
        System.out.println("Duck is flying.");
    }

    public void swim() {
        System.out.println("Duck is swimming.");
    }
}

public class Main {
    public static void main(String[] args) {
        Duck duck = new Duck();
        duck.fly();  // Output: Duck is flying.
        duck.swim(); // Output: Duck is swimming.
    }
}
```

### Functional interface

```java
// Functional interface
interface Greeting {
    void greet(String name);
}

public class Main {
    public static void main(String[] args) {
        // Implement the interface using a lambda expression
        Greeting greeting = (name) -> System.out.println("Hello, " + name + "!");
        greeting.greet("Alice"); // Output: Hello, Alice!
    }
}
```

### Immutable classes

```java
import java.util.Date;

// Step 1: Declare the class as final
public final class ImmutablePerson {
    // Step 2: Make all fields private and final
    private final String name;
    private final int age;
    private final Date birthDate; // Mutable field

    // Step 4: Initialize all fields via a constructor
    public ImmutablePerson(String name, int age, Date birthDate) {
        this.name = name;
        this.age = age;
        // Step 5: Perform deep copying for mutable fields
        this.birthDate = new Date(birthDate.getTime());
    }

    // Step 3: Do not provide setter methods

    // Provide only getter methods
    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    // Return a copy of the mutable field
    public Date getBirthDate() {
        return new Date(birthDate.getTime());
    }

    @Override
    public String toString() {
        return "ImmutablePerson{" +
                "name='" + name + '\'' +
                ", age=" + age +
                ", birthDate=" + birthDate +
                '}';
    }
}
```
## Enum

```java
public enum Planet {
    MERCURY(3.303e+23, 2.4397e6),
    VENUS(4.869e+24, 6.0518e6),
    EARTH(5.976e+24, 6.37814e6),
    MARS(6.421e+23, 3.3972e6),
    JUPITER(1.9e+27, 7.1492e7),
    SATURN(5.688e+26, 6.0268e7),
    URANUS(8.686e+25, 2.5559e7),
    NEPTUNE(1.024e+26, 2.4746e7);

    private final double mass;   // in kilograms
    private final double radius; // in meters

    Planet(double mass, double radius) {
        this.mass = mass;
        this.radius = radius;
    }

    public double getMass() {
        return mass;
    }

    public double getRadius() {
        return radius;
    }

    public double getSurfaceGravity() {
        return 6.67300E-11 * mass / (radius * radius);
    }

    public double getSurfaceWeight(double otherMass) {
        return otherMass * getSurfaceGravity();
    }
}
```

## Wrapper Classes
### 1. Creating Wrapper Objects

```Java
// Using constructors (deprecated in Java 9+)
Integer intObj = new Integer(10);
Double doubleObj = new Double(3.14);

// Using static factory methods (recommended)
Integer intObj2 = Integer.valueOf(10);
Double doubleObj2 = Double.valueOf(3.14);
```

### 2. Autoboxing and Unboxing
```java
// Autoboxing: Primitive to Wrapper
int num = 42;
Integer wrappedNum = num; // Autoboxing

// Unboxing: Wrapper to Primitive
int unwrappedNum = wrappedNum; // Unboxing
```

### 3. Utility Methods
```java
// Converting String to int
String numberStr = "123";
int parsedInt = Integer.parseInt(numberStr);

// Converting int to String
int num = 456;
String numStr = Integer.toString(num);

// Comparing two Integer objects
Integer a = 10;
Integer b = 20;
int comparison = a.compareTo(b); // Returns -1 (a < b)
```

### 4. Using Wrapper Classes in Collections
```java
import java.util.ArrayList;
import java.util.List;

public class Main {
    public static void main(String[] args) {
        List<Integer> numbers = new ArrayList<>();
        numbers.add(10); // Autoboxing: int to Integer
        numbers.add(20);

        int firstNumber = numbers.get(0); // Unboxing: Integer to int
        System.out.println("First number: " + firstNumber);
    }
}
```

**Integer Class:**
int parseInt(String s): Converts a string to an int.
String toString(int i): Converts an int to a string.
int compareTo(Integer anotherInteger): Compares two Integer objects.
Integer valueOf(int i): Returns an Integer instance representing the specified int value.

**Double Class:**
double parseDouble(String s): Converts a string to a double.
String toString(double d): Converts a double to a string.
int compareTo(Double anotherDouble): Compares two Double objects.
Double valueOf(double d): Returns a Double instance representing the specified double value.

**Character Class:**
boolean isDigit(char ch): Checks if a character is a digit.
boolean isLetter(char ch): Checks if a character is a letter.
char toUpperCase(char ch): Converts a character to uppercase.
char toLowerCase(char ch): Converts a character to lowercase.

**Boolean Class:**
boolean parseBoolean(String s): Converts a string to a boolean.
String toString(boolean b): Converts a boolean to a string.
boolean compareTo(Boolean anotherBoolean): Compares two Boolean objects.
Boolean valueOf(boolean b): Returns a Boolean instance representing the specified boolean value.

## Full Implementation of equals() and hashCode()
```java
class Person {
    private String name;
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public boolean equals(Object obj) {
        if (this == obj) return true;
        if (obj == null || getClass() != obj.getClass()) return false;
        Person person = (Person) obj;
        return age == person.age && name.equals(person.name);
    }

    @Override
    public int hashCode() {
        int result = 17;
        result = 31 * result + name.hashCode();
        result = 31 * result + age;
        return result;
    }

    @Override
    public String toString() {
        return "Person{name='" + name + "', age=" + age + "}";
    }
}

public class Main {
    public static void main(String[] args) {
        Person person1 = new Person("Alice", 25);
        Person person2 = new Person("Alice", 25);

        System.out.println("person1.equals(person2): " + person1.equals(person2)); // true
        System.out.println("person1.hashCode(): " + person1.hashCode()); // Same hash code
        System.out.println("person2.hashCode(): " + person2.hashCode()); // Same hash code
    }
}
```

