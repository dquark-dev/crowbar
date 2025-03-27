
## Obtaining a Stream

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Stream;

public class StreamExample {
    public static void main(String[] args) {
        // Obtain a stream from a list
        List<String> fruits = Arrays.asList("Apple", "Banana", "Cherry", "Date");
        Stream<String> stream1 = fruits.stream();

        // Obtain a stream from an array
        String[] colors = {"Red", "Green", "Blue"};
        Stream<String> stream2 = Arrays.stream(colors);

        // Obtain a stream using Stream.of()
        Stream<String> stream3 = Stream.of("One", "Two", "Three");

        System.out.println("Stream from list: " + stream1.count()); // Output: 4
        System.out.println("Stream from array: " + stream2.count()); // Output: 3
        System.out.println("Stream from Stream.of(): " + stream3.count()); // Output: 3
    }
}
```

## Stream Operations
### Intermediate Opeerations
#### filter

```java
import java.util.Arrays;
import java.util.List;

public class FilterExample {
    public static void main(String[] args) {
        List<String> fruits = Arrays.asList("Apple", "Banana", "Cherry", "Date");

        // Filter fruits starting with 'A'
        fruits.stream()
              .filter(fruit -> fruit.startsWith("A"))
              .forEach(System.out::println); // Output: Apple
    }
}
```

#### map

```java
import java.util.Arrays;
import java.util.List;

public class MapExample {
    public static void main(String[] args) {
        List<String> fruits = Arrays.asList("Apple", "Banana", "Cherry", "Date");

        // Convert each fruit to uppercase
        fruits.stream()
              .map(String::toUpperCase)
              .forEach(System.out::println);
    }
}

```

#### distinct

```java
import java.util.Arrays;
import java.util.List;

public class DistinctExample {
    public static void main(String[] args) {
        List<String> fruits = Arrays.asList("Apple", "Banana", "Cherry", "Apple");

        // Remove duplicates
        fruits.stream()
              .distinct()
              .forEach(System.out::println);
    }
}
```

#### limit

```java
import java.util.Arrays;
import java.util.List;

public class LimitExample {
    public static void main(String[] args) {
        List<String> fruits = Arrays.asList("Apple", "Banana", "Cherry", "Date");

        // Limit to the first 2 fruits
        fruits.stream()
              .limit(2)
              .forEach(System.out::println);
    }
}
```

#### sorted
```java
import java.util.Arrays;
import java.util.List;

public class SortedExample {
    public static void main(String[] args) {
        List<String> fruits = Arrays.asList("Apple", "Banana", "Cherry", "Date");

        // Sort the fruits alphabetically
        fruits.stream()
              .sorted()
              .forEach(System.out::println);
    }
}
```

### terminal operations
#### forEach

```java
import java.util.Arrays;
import java.util.List;

public class ForEachExample {
    public static void main(String[] args) {
        List<String> fruits = Arrays.asList("Apple", "Banana", "Cherry", "Date");

        // Print each fruit
        fruits.stream()
              .forEach(System.out::println);
    }
}
```

#### reduce

```java
import java.util.Arrays;
import java.util.List;

public class ReduceExample {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);

        // Sum all numbers
        int sum = numbers.stream()
                         .reduce(0, (a, b) -> a + b);

        System.out.println("Sum: " + sum); // Output: 15
    }
}
```

#### count

```java
import java.util.Arrays;
import java.util.List;

public class CountExample {
    public static void main(String[] args) {
        List<String> fruits = Arrays.asList("Apple", "Banana", "Cherry", "Date");

        // Count the number of fruits
        long count = fruits.stream()
                           .count();

        System.out.println("Count: " + count); // Output: 4
    }
}
```

#### min and max

```java
import java.util.Arrays;
import java.util.List;
import java.util.Optional;

public class MinMaxExample {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(5, 3, 8, 1, 10);

        // Find the minimum number
        Optional<Integer> min = numbers.stream()
                                       .min(Integer::compareTo);

        // Find the maximum number
        Optional<Integer> max = numbers.stream()
                                       .max(Integer::compareTo);

        System.out.println("Min: " + min.orElse(-1)); // Output: 1
        System.out.println("Max: " + max.orElse(-1)); // Output: 10
    }
}
```

#### collect

```java
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;

public class CollectExample {
    public static void main(String[] args) {
        List<String> fruits = Arrays.asList("Apple", "Banana", "Cherry", "Date");

        // Collect fruits into a list
        List<String> filteredFruits = fruits.stream()
                                            .filter(fruit -> fruit.startsWith("A"))
                                            .collect(Collectors.toList());

        System.out.println("Filtered fruits: " + filteredFruits); // Output: [Apple]
    }
}
```

Key Points
- Streams provide a declarative way to process collections.
- Stream operations are either intermediate (e.g., filter, map, sorted) or terminal (e.g., forEach, collect, reduce).
- Streams are lazy, meaning intermediate operations are only executed when a terminal operation is invoked.

