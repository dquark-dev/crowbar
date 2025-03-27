
A sequence of elements supporting sequential and parallel aggregate operations. The following example illustrates an aggregate operation using Stream and IntStream:

```java
int sum = widgets.stream()
                      .filter(w -> w.getColor() == RED)
                      .mapToInt(w -> w.getWeight())
                      .sum();
```

To perform a computation, stream operations are composed into a stream pipeline.
A stream pipeline consists of a **source (which might be an array, a collection, a generator function, an I/O channel**, etc), **zero or more intermediate operations** (which transform a stream into another stream, such as **filter(Predicate))**, and a terminal operation (which produces a result or side-effect, such as **count()** or **forEach(Consumer))**. 
Streams are lazy; computation on the source data is only performed when the **terminal operation is initiated**, and source elements are consumed only as needed.

**Source**
**Intermediate Operations**
**Terminal Operations**


