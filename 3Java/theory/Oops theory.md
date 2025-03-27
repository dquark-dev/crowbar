| Access Specifier | Same Class | Same Package | Subclass (Different Package) | Different Package |
| ---------------- | ---------- | ------------ | ---------------------------- | ----------------- |
| `public`         | Yes        | Yes          | Yes                          | Yes               |
| `private`        | Yes        | No           | No                           | No                |
| `protected`      | Yes        | Yes          | Yes                          | No                |
| `default`        | Yes        | Yes          | No                           | No                |

## Key Features of Interfaces:

- Abstract Methods: Interfaces can declare methods without providing an implementation. The implementing class must provide the implementation.
- Constants: Interfaces can contain constants (public, static, and final by default).
- Multiple Inheritance: A class can implement multiple interfaces, allowing it to inherit behavior from multiple sources.
- Default and Static Methods: Starting from Java 8, interfaces can have default methods (methods with a body) and static methods.
- Functional Interfaces: An interface with exactly one abstract method is called a functional interface and can be used with lambda expressions.

**Implementing an Interface**
A class implements an interface using the implements keyword. The class must provide implementations for all the abstract methods declared in the interface.

When to Use Interfaces:
- Abstraction: When you want to define a contract without providing implementation.
- Multiple Inheritance: When a class needs to inherit behavior from multiple sources.
- Loose Coupling: When you want to decouple the implementation from the interface.
- Functional Programming: When working with lambda expressions and functional programming.

### Differences Between Interfaces and Abstract Classes:

| Feature                  | Interface                              | Abstract Class                        |
| ------------------------ | -------------------------------------- | ------------------------------------- |
| **Methods**              | Abstract, default, static methods      | Abstract and concrete methods         |
| **Fields**               | Only constants (public, static, final) | Can have instance and static fields   |
| **Multiple Inheritance** | Supports multiple inheritance          | Does not support multiple inheritance |
| **Constructor**          | No constructors                        | Can have constructors                 |
| **Usage**                | Define contracts and behavior          | Provide partial implementation        |
