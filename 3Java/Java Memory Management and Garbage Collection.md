
2 Types of Memory
---------------------------------------
- STACK
- HEAP

Both Stack and Heap are created by JVM and stored in RAM

Stack Memory
- Store Temporary Variables and separate memory block for methods
- Store Primitive data types
- Store Reference of the heap objects
	- Strong references
	- Weak reference
		- Soft references
- Each thread has its own Stack memory
- Variables with a SCOPE is only visible and as soon as any variable goes out of the SCOPE, it get deleted from the Stack (in LIFO order)
- When Stack memory goes full, its throws "java.lang.StackOverflowError"

Heap Memory
- Store Objects
- There is no order of allocating the memory
- Garbage Collector is used to delete the unreferenced objects from the heap
	- Mark and Sweep Algorithm 
	- Types of GC
		- Single GC
		- Parallel GC
		- CMS (concurrent Mark sweep)
		- G1
- Heap memory is shared with all the threads
- Heap also contains the String Pool
- When Heap memory goes full, its throws "java.lang.OutofMemoryError"
- Heap memory is further divided into:
	- Young Generation (minor GC happens here)
		- Eden
		- Survivor
	- Old/Tenured Generation (major GC happens here)
	- Permanent Generation