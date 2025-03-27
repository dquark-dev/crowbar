## **Conversion of Primitive to Object (Boxing)**

Primitive Data Types and Their Corresponding Wrapper Classes:

| **Primitive Data Type** | **Wrapper Class** |
| ----------------------- | ----------------- |
| `byte`                  | `Byte`            |
| `short`                 | `Short`           |
| `int`                   | `Integer`         |
| `long`                  | `Long`            |
| `float`                 | `Float`           |
| `double`                | `Double`          |
| `char`                  | `Character`       |
| `boolean`               | `Boolean`         |
The process of converting a primitive data type into its corresponding wrapper class object is called boxing. This can be done explicitly or automatically (autoboxing).
### Explicit boxing

```java
int primitiveInt = 42;
Integer objectInt = Integer.valueOf(primitiveInt); // Explicit boxing

double primitiveDouble = 3.14;
Double objectDouble = new Double(primitiveDouble); // Explicit boxing (constructor)
```
## Conversion of Object to Primitive (UnBoxing)

```java
Integer objectInt = Integer.valueOf(42);
int primitiveInt = objectInt.intValue(); // Explicit unboxing

Double objectDouble = Double.valueOf(3.14);
double primitiveDouble = objectDouble.doubleValue(); // Explicit unboxing
```

```java
import java.util.ArrayList;
import java.util.List;

public class Main {
    public static void main(String[] args) {
        // Using Integer wrapper class for int primitives
        List<Integer> numbers = new ArrayList<>();
        numbers.add(10); // Autoboxing: int to Integer
        numbers.add(20);
        numbers.add(30);

        // Accessing elements
        int firstNumber = numbers.get(0); // Auto-unboxing: Integer to int
        System.out.println("First number: " + firstNumber);
    }
}
```

Since collections like `ArrayList` or `HashMap` can only store objects, you must use wrapper classes for primitives.
### Key Points:
1. **Wrapper Classes**: Each primitive type has a corresponding wrapper class. 
2. **Boxing**: Converting a primitive to an object (explicit or autoboxing).
3. **Unboxing**: Converting an object back to a primitive (explicit or auto-unboxing).
4. **Use Cases**:
- Storing primitives in collections.
- Using primitives in generic types (e.g., `List<Integer>`).
- Passing primitives to methods that require objects.
### Performance Considerations:
- **Autoboxing and Unboxing**: While convenient, they can introduce performance overhead in tight loops or large-scale applications because they involve object creation and method calls.
- **Primitive Arrays**: For performance-critical applications, prefer using primitive arrays (e.g., `int[]`) instead of collections of wrapper objects.
### Summary:

| Operation         | Example                              |
| ----------------- | ------------------------------------ |
| **Boxing**        | `Integer obj = Integer.valueOf(42);` |
| **Autoboxing**    | `Integer obj = 42;`                  |
| **Unboxing**      | `int primitive = obj.intValue();`    |
| **Auto-Unboxing** | `int primitive = obj;`               |

Wrapper classes bridge the gap between primitives and objects, enabling primitives to be used in object-oriented contexts.

## String to Primitive

**1. String to Custom Object**

```java
class Person {
    String name;
    int age;

    // Constructor
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return "Person{name='" + name + "', age=" + age + "}";
    }
}

public class Main {
    public static void main(String[] args) {
        String input = "John,30";

        // Split the String and create a Person object
        String[] parts = input.split(",");
        String name = parts[0];
        int age = Integer.parseInt(parts[1]); //parse

        Person person = new Person(name, age);
        System.out.println(person);
    }
}
```

**2. String to Wrapper Class Objects**

You can convert a `String` to wrapper class objects (e.g., `Integer`, `Double`, `Boolean`, etc.) using their respective `valueOf()` or `parseXXX()` methods.

```java
public class Main {
    public static void main(String[] args) {
        String numberStr = "123";
        String doubleStr = "45.67";
        String booleanStr = "true";

        // Convert String to Integer
        Integer number = Integer.valueOf(numberStr); // or Integer.parseInt(numberStr)

        // Convert String to Double
        Double decimal = Double.valueOf(doubleStr); // or Double.parseDouble(doubleStr)

        // Convert String to Boolean
        Boolean bool = Boolean.valueOf(booleanStr); // or Boolean.parseBoolean(booleanStr)

        System.out.println("Integer: " + number);
        System.out.println("Double: " + decimal);
        System.out.println("Boolean: " + bool);
    }
}
```

**3. String to Date Object**
You can convert a `String` to a `Date` object using the `SimpleDateFormat` class.

```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class Main {
    public static void main(String[] args) {
        String dateStr = "2023-10-25";

        // Define the date format
        SimpleDateFormat format = new SimpleDateFormat("yyyy-MM-dd");

        try {
            // Convert String to Date
            Date date = format.parse(dateStr);
            System.out.println("Date: " + date);
        } catch (ParseException e) {
            System.out.println("Invalid date format");
        }
    }
}
```

**5. String to Enum**
If you have an enum, you can convert a String to an enum constant using the valueOf() method.

```java
enum Day {
    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY
}

public class Main {
    public static void main(String[] args) {
        String dayStr = "WEDNESDAY";

        // Convert String to Enum
        Day day = Day.valueOf(dayStr);

        System.out.println("Day: " + day);
    }
}
```

**6. String to Array or List**
```Java
import java.util.Arrays;
import java.util.List;

public class Main {
    public static void main(String[] args) {
        String input = "apple,banana,orange";

        // Convert String to Array
        String[] array = input.split(",");
        System.out.println("Array: " + Arrays.toString(array));

        // Convert String to List
        List<String> list = Arrays.asList(array);
        System.out.println("List: " + list);
    }
}
```

**4. String to JSON Object**
If you have a JSON string, you can convert it to a JSON object using libraries like Jackson or Gson.

```java
import com.google.gson.Gson;

class User {
    String name;
    int age;

    @Override
    public String toString() {
        return "User{name='" + name + "', age=" + age + "}";
    }
}

public class Main {
    public static void main(String[] args) {
        String jsonStr = "{\"name\":\"Alice\",\"age\":25}";

        // Convert JSON String to User object
        Gson gson = new Gson();
        User user = gson.fromJson(jsonStr, User.class);

        System.out.println(user);
    }
}
```
### Summary:

| Target Object Type | Method/Approach                                                          |
| ------------------ | ------------------------------------------------------------------------ |
| **Custom Object**  | Parse the `String` and initialize the object's fields.                   |
| **Wrapper Class**  | Use `valueOf()` or `parseXXX()` methods (e.g., `Integer.valueOf()`).     |
| **Date Object**    | Use `SimpleDateFormat` to parse the `String`.                            |
| **JSON Object**    | Use libraries like Gson or Jackson to deserialize the `String`.          |
| **Enum**           | Use the `valueOf()` method of the enum.                                  |
| **Array or List**  | Use `split()` to create an array and `Arrays.asList()` to create a list. |

In Java, converting a `String` to an object depends on the target object type and often involves parsing or deserialization.