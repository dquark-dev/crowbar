
```java
public class LambdaExample {
    public static void main(String[] args) {
        // Without lambda
        Runnable runnable1 = new Runnable() {
            @Override
            public void run() {
                System.out.println("Running without lambda");
            }
        };
        runnable1.run();

        // With lambda
        Runnable runnable2 = () -> System.out.println("Running with lambda");
        runnable2.run();
    }
}
```

n Java, lambda expressions provide a clear and concise way to represent instances of functional interfaces (interfaces with a single abstract method). They are widely used with the Java Streams API, event listeners, and functional programming constructs.

## Lambda with Parameters

```java
import java.util.Arrays;
import java.util.Comparator;

public class LambdaWithParameters {
    public static void main(String[] args) {
        String[] fruits = {"Apple", "Banana", "Cherry", "Date"};

        // Without lambda
        Arrays.sort(fruits, new Comparator<String>() {
            @Override
            public int compare(String s1, String s2) {
                return s1.compareTo(s2);
            }
        });

        // With lambda
        Arrays.sort(fruits, (s1, s2) -> s1.compareTo(s2));

        System.out.println("Sorted fruits: " + Arrays.toString(fruits));
    }
}
```

## Lambda with Multiple Statements

```java
public class LambdaMultipleStatements {
    public static void main(String[] args) {
        // Lambda with multiple statements
        Runnable runnable = () -> {
            System.out.println("Statement 1");
            System.out.println("Statement 2");
        };
        runnable.run();
    }
}
```

## Lambda with Return Statement

```java
import java.util.function.Function;

public class LambdaReturnExample {
    public static void main(String[] args) {
        // Lambda with return statement
        Function<Integer, Integer> square = (x) -> {
            return x * x;
        };

        // Lambda without return statement (single expression)
        Function<Integer, Integer> cube = (x) -> x * x * x;

        System.out.println("Square of 5: " + square.apply(5));
        System.out.println("Cube of 5: " + cube.apply(5));
    }
}
```

## Lambda with Streams API

```java
import java.util.Arrays;
import java.util.List;

public class LambdaWithStreams {
    public static void main(String[] args) {
        List<String> fruits = Arrays.asList("Apple", "Banana", "Cherry", "Date");

        // Filter and print fruits starting with 'A'
        fruits.stream()
              .filter(fruit -> fruit.startsWith("A"))
              .forEach(System.out::println);
    }
}
```

## Lambda with Custom Functional Interface

```java
// Custom functional interface
interface MathOperation {
    int operate(int a, int b);
}

public class CustomFunctionalInterfaceExample {
    public static void main(String[] args) {
        // Lambda to add two numbers
        MathOperation addition = (a, b) -> a + b;

        // Lambda to multiply two numbers
        MathOperation multiplication = (a, b) -> a * b;

        System.out.println("Addition: " + addition.operate(5, 3));
        System.out.println("Multiplication: " + multiplication.operate(5, 3));
    }
}
```

## Lambda with Method References

```java
import java.util.Arrays;
import java.util.List;

public class MethodReferenceExample {
    public static void main(String[] args) {
        List<String> fruits = Arrays.asList("Apple", "Banana", "Cherry", "Date");

        // Using lambda expression
        fruits.forEach(fruit -> System.out.println(fruit));

        // Using method reference
        fruits.forEach(System.out::println);
    }
}
```

## Lambda with Predicate

```java
import java.util.Arrays;
import java.util.List;
import java.util.function.Predicate;

public class PredicateExample {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

        // Lambda to filter even numbers
        Predicate<Integer> isEven = (n) -> n % 2 == 0;

        // Filter and print even numbers
        numbers.stream()
               .filter(isEven)
               .forEach(System.out::println);
    }
}
```

- Lambda expressions provide a concise way to implement functional interfaces.
- They can take parameters, return values, and contain multiple statements.
- They are widely used with the Streams API, event listeners, and functional programming constructs.
- Method references provide a shorthand for lambda expressions that call existing methods.

