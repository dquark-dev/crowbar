
### **Comparison Table** ArrayList, LinkedList, Vector

| Feature                 | ArrayList                 | LinkedList                   | Vector                     |
| ----------------------- | ------------------------- | ---------------------------- | -------------------------- |
| **Internal Structure**  | Dynamic array             | Doubly linked list           | Dynamic array              |
| **Random Access**       | O(1)                      | O(n)                         | O(1)                       |
| **Insertions/Removals** | O(n) (slow in the middle) | O(1) (fast at ends)          | O(n) (slow in the middle)  |
| **Thread Safety**       | Not thread-safe           | Not thread-safe              | Thread-safe (synchronized) |
| **Use Case**            | Frequent access by index  | Frequent insertions/removals | Thread-safe requirements   |

### **Comparison Table** HashSet, LinkedHashSet, TreeSet

| Feature                | HashSet                              | LinkedHashSet             | TreeSet                                  |
| ---------------------- | ------------------------------------ | ------------------------- | ---------------------------------------- |
| **Internal Structure** | Hash table                           | Hash table + linked list  | Red-Black tree                           |
| **Ordering**           | Unordered                            | Insertion order           | Sorted order                             |
| **Performance**        | O(1) for `add`, `remove`, `contains` | O(1) with slight overhead | O(log n) for `add`, `remove`, `contains` |
| **Thread Safety**      | Not thread-safe                      | Not thread-safe           | Not thread-safe                          |
| **Use Case**           | Fast operations, no ordering         | Insertion order required  | Sorted order required                    |

### **Comparison Table** HashMap, LinkedHashMap, TreeMap

| Feature                | HashMap                         | LinkedHashMap                             | TreeMap                             |
| ---------------------- | ------------------------------- | ----------------------------------------- | ----------------------------------- |
| **Internal Structure** | Hash table                      | Hash table + linked list                  | Red-Black tree                      |
| **Ordering**           | Unordered                       | Insertion order (default) or access order | Sorted order                        |
| **Performance**        | O(1) for `put`, `get`, `remove` | O(1) with slight overhead                 | O(log n) for `put`, `get`, `remove` |
| **Thread Safety**      | Not thread-safe                 | Not thread-safe                           | Not thread-safe                     |
| **Use Case**           | Fast operations, no ordering    | Insertion/access order required           | Sorted order required               |
