## Arrays

```java
public class ArrayExample {
    public static void main(String[] args) {
        // Declare and initialize an array of integers
        int[] numbers = {10, 20, 30, 40, 50};

        // Access and print array elements
        for (int i = 0; i < numbers.length; i++) {
            System.out.println("Element at index " + i + ": " + numbers[i]);
        }
    }
}
```

```java
import java.util.Arrays;

public class ArraysUtilityExample {
    public static void main(String[] args) {
        int[] numbers = {5, 3, 9, 1, 7};

        // Sort the array
        Arrays.sort(numbers);
        System.out.println("Sorted array: " + Arrays.toString(numbers));

        // Search for an element
        int index = Arrays.binarySearch(numbers, 7);
        System.out.println("Index of 7: " + index);

        // Fill the array with a value
        Arrays.fill(numbers, 0);
        System.out.println("Array after fill: " + Arrays.toString(numbers));
    }
}
```

- Arrays are fixed in size once declared.
- Array indices start at 0 and go up to length - 1.
- Use array.length to get the size of an array.
- Use the Arrays utility class for common operations like sorting and searching.
- Multidimensional arrays are arrays of arrays.
- Arrays are used to store collections of data of the same type.
- They can be single-dimensional or multidimensional.
- Use loops to iterate over arrays.
- The Arrays utility class provides helpful methods for working with arrays.

## List, List interface
ArrayList, LinkedList, Vector
### ArrayList

```java
import java.util.ArrayList;

public class ArrayListExample {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("Apple");
        list.add("Banana");
        list.add("Cherry");

        System.out.println("ArrayList: " + list);
    }
}
```

- Internal Implementation: Uses a dynamic array to store elements.
- Resizable: Automatically resizes itself when elements are added or removed.
- Performance:
	- Fast random access: O(1) time complexity for accessing elements by index.
	- Slow insertions/removals: O(n) time complexity for adding or removing elements in the middle of the list, as elements need to be shifted.
- Thread Safety: Not thread-safe (use *Collections.synchronizedList* for thread safety).
- Use Case: Best for scenarios where frequent access to elements by index is required, and insertions/removals are mostly at the end of the list.

### Linked List
```java
import java.util.LinkedList;

public class LinkedListExample {
    public static void main(String[] args) {
        LinkedList<String> list = new LinkedList<>();
        list.add("Apple");
        list.add("Banana");
        list.add("Cherry");

        System.out.println("LinkedList: " + list);
    }
}
```

- Internal Implementation: Uses a doubly linked list to store elements.
- Resizable: Automatically resizes itself when elements are added or removed.
- Performance:
	- Slow random access: O(n) time complexity for accessing elements by index, as traversal is required.
	- Fast insertions/removals: O(1) time complexity for adding or removing elements at the beginning or end of the list.
- Thread Safety: Not thread-safe (use Collections.synchronizedList for thread safety).
- Use Case: Best for scenarios where frequent insertions/removals are required, especially at the beginning or middle of the list.

## Set, Set interface

### HashSet

```java
import java.util.HashSet;

public class HashSetExample {
    public static void main(String[] args) {
        HashSet<String> set = new HashSet<>();
        set.add("Apple");
        set.add("Banana");
        set.add("Cherry");

        System.out.println("HashSet: " + set); // Order is not guaranteed
    }
}
```

### LinkedHashSet

```java
import java.util.LinkedHashSet;

public class LinkedHashSetExample {
    public static void main(String[] args) {
        LinkedHashSet<String> set = new LinkedHashSet<>();
        set.add("Apple");
        set.add("Banana");
        set.add("Cherry");

        System.out.println("LinkedHashSet: " + set); // Maintains insertion order
    }
}
```

### TreeSet

```java
import java.util.TreeSet;

public class TreeSetExample {
    public static void main(String[] args) {
        TreeSet<String> set = new TreeSet<>();
        set.add("Apple");
        set.add("Banana");
        set.add("Cherry");

        System.out.println("TreeSet: " + set); // Maintains sorted order
    }
}
```

Summary:
- HashSet: Fastest, unordered(changes order when added or el removed).
- LinkedHashSet: Maintains insertion order, slightly slower than HashSet.
- TreeSet: Maintains sorted order, slower than both HashSet and LinkedHashSet.

## Map Interface

### HashMap

```java
import java.util.HashMap;

public class HashMapExample {
    public static void main(String[] args) {
        // Create a HashMap
        HashMap<String, Integer> map = new HashMap<>();

        // Add key-value pairs
        map.put("Apple", 10);
        map.put("Banana", 20);
        map.put("Cherry", 30);

        // Print the HashMap
        System.out.println("HashMap: " + map);

        // Access a value using a key
        System.out.println("Quantity of Apple: " + map.get("Apple"));

        // Remove a key-value pair
        map.remove("Banana");
        System.out.println("HashMap after removal: " + map);
    }
}
```

- Internal Implementation: Uses a hash table (backed by an array of buckets) to store key-value pairs.
- Ordering: Does not maintain any order of keys (unordered).
- Performance:
	- Fast operations: O(1) average time complexity for put, get, and remove.
- Thread Safety: Not thread-safe (use Collections.synchronizedMap or ConcurrentHashMap for thread safety).
- Use Case: Best for scenarios where you need fast operations and do not care about the order of keys.
### LinkedHashMap

```java
import java.util.LinkedHashMap;

public class LinkedHashMapExample {
    public static void main(String[] args) {
        // Create a LinkedHashMap
        LinkedHashMap<String, Integer> map = new LinkedHashMap<>();

        // Add key-value pairs
        map.put("Apple", 10);
        map.put("Banana", 20);
        map.put("Cherry", 30);

        // Print the LinkedHashMap
        System.out.println("LinkedHashMap: " + map);

        // Access a value using a key
        System.out.println("Quantity of Banana: " + map.get("Banana"));

        // Remove a key-value pair
        map.remove("Cherry");
        System.out.println("LinkedHashMap after removal: " + map);
    }
}
```

- Internal Implementation: Uses a hash table with a linked list to maintain insertion order or access order (if configured).
- Ordering: Maintains the insertion order of keys by default. Can also maintain access order (least recently used to most recently used) if configured.
- Performance:
	- Slightly slower than HashMap: O(1) average time complexity for put, get, and remove, but with slightly higher overhead due to maintaining the linked list.
- Thread Safety: Not thread-safe (use Collections.synchronizedMap for thread safety).
- Use Case: Best for scenarios where you need to maintain the insertion or access order of keys while still having fast operations.
### TreeMap

```java
import java.util.TreeMap;

public class TreeMapExample {
    public static void main(String[] args) {
        // Create a TreeMap
        TreeMap<String, Integer> map = new TreeMap<>();

        // Add key-value pairs
        map.put("Apple", 10);
        map.put("Banana", 20);
        map.put("Cherry", 30);

        // Print the TreeMap
        System.out.println("TreeMap: " + map);

        // Access a value using a key
        System.out.println("Quantity of Cherry: " + map.get("Cherry"));

        // Remove a key-value pair
        map.remove("Banana");
        System.out.println("TreeMap after removal: " + map);
    }
}
```

- Internal Implementation: Uses a Red-Black tree (a self-balancing binary search tree) to store key-value pairs.
- Ordering: Maintains keys in sorted order (natural order or custom order defined by a Comparator).
- Performance:
	- Slower than HashMap and LinkedHashMap: O(log n) time complexity for put, get, and remove.
- Thread Safety: Not thread-safe (use Collections.synchronizedMap for thread safety).
- Use Case: Best for scenarios where you need keys to be sorted.