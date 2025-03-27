## Strings Class

```java
public class StringExample {
    public static void main(String[] args) {
        String str = "Hello";
        str = str + " World"; // Creates a new String object

        System.out.println(str); // Output: Hello World
    }
}
```

- Immutable: Once a String object is created, its value cannot be changed. Any operation that modifies the string (e.g., concatenation) creates a new String object.
- Performance: Operations like concatenation can be inefficient because they create new objects in memory.
- Thread Safety: Since String is immutable, it is inherently thread-safe.
- Use Case: Best for scenarios where the text is constant and does not change frequently.

```java
public class StringMethodsExample {
    public static void main(String[] args) {
        String str1 = "Hello World";
        String str2 = "hello world";
        String str3 = "   Trim Me   ";
        String str4 = "Java is fun, Java is powerful";

        // char charAt(int index)
        System.out.println("charAt(6): " + str1.charAt(6)); // Output: W

        // int compareTo(String str)
        System.out.println("compareTo(\"Hello World\"): " + str1.compareTo("Hello World")); // Output: 0 (equal)
        System.out.println("compareTo(\"Hello\"): " + str1.compareTo("Hello")); // Output: positive (str1 is longer)

        // int compareToIgnoreCase(String str)
        System.out.println("compareToIgnoreCase(\"hello world\"): " + str1.compareToIgnoreCase(str2)); // Output: 0 (equal ignoring case)

        // String concat(String str)
        System.out.println("concat(\"!\"): " + str1.concat("!")); // Output: Hello World!

        // boolean endsWith(String suffix)
        System.out.println("endsWith(\"World\"): " + str1.endsWith("World")); // Output: true

        // boolean equals(Object anObject)
        System.out.println("equals(\"Hello World\"): " + str1.equals("Hello World")); // Output: true

        // boolean equalsIgnoreCase(String anotherString)
        System.out.println("equalsIgnoreCase(\"hello world\"): " + str1.equalsIgnoreCase(str2)); // Output: true

        // int hashCode()
        System.out.println("hashCode(): " + str1.hashCode()); // Output: hash code of "Hello World"

        // String toLowerCase()
        System.out.println("toLowerCase(): " + str1.toLowerCase()); // Output: hello world

        // String toUpperCase()
        System.out.println("toUpperCase(): " + str1.toUpperCase()); // Output: HELLO WORLD

        // String trim()
        System.out.println("trim(): " + str3.trim()); // Output: Trim Me

        // int length()
        System.out.println("length(): " + str1.length()); // Output: 11

        // String replace(char oldChar, char newChar)
        System.out.println("replace('o', 'a'): " + str1.replace('o', 'a')); // Output: Hella Warld

        // String replaceAll(String regex, String replacement)
        System.out.println("replaceAll(\"Java\", \"Python\"): " + str4.replaceAll("Java", "Python")); // Output: Python is fun, Python is powerful

        // String replaceFirst(String regex, String replacement)
        System.out.println("replaceFirst(\"Java\", \"Python\"): " + str4.replaceFirst("Java", "Python")); // Output: Python is fun, Java is powerful

        // String[] split(String regex, [int limit])
        String[] splitResult = str4.split(" ");
        System.out.println("split(\" \"): ");
        for (String s : splitResult) {
            System.out.println(s);
        }
        // Output:
        // Java
        // is
        // fun,
        // Java
        // is
        // powerful

        // boolean startsWith(String prefix)
        System.out.println("startsWith(\"Hello\"): " + str1.startsWith("Hello")); // Output: true

        // String substring(int beginIndex)
        System.out.println("substring(6): " + str1.substring(6)); // Output: World

        // String substring(int beginIndex, int endIndex)
        System.out.println("substring(0, 5): " + str1.substring(0, 5)); // Output: Hello

        // char[] toCharArray()
        char[] charArray = str1.toCharArray();
        System.out.println("toCharArray(): ");
        for (char c : charArray) {
            System.out.print(c + " ");
        }
        // Output: H e l l o   W o r l d

        // String toString()
        System.out.println("\ntoString(): " + str1.toString()); // Output: Hello World
    }
}
```
## Strings Buffer Class

```java
public class StringBufferExample {
    public static void main(String[] args) {
        StringBuffer sb = new StringBuffer("Hello");
        sb.append(" World"); // Modifies the existing object

        System.out.println(sb); // Output: Hello World
    }
}
```

- Mutable: The value of a StringBuffer object can be changed after it is created. It provides methods to modify the content (e.g., append, insert, delete).
- Performance: More efficient than String for frequent modifications because it avoids creating new objects.
- Thread Safety: StringBuffer is thread-safe because its methods are synchronized.
- Use Case: Best for scenarios where the text is modified frequently, especially in a multi-threaded environment.