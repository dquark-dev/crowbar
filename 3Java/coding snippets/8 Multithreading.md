## Thread methods
sleep, yield, join

### sleep

```java
public class SleepExample {
    public static void main(String[] args) {
        Runnable task = () -> {
            for (int i = 1; i <= 5; i++) {
                System.out.println(Thread.currentThread().getName() + ": " + i);
                try {
                    Thread.sleep(1000); // Pause for 1 second
                } catch (InterruptedException e) {
                    System.out.println("Thread interrupted");
                }
            }
        };

        Thread thread = new Thread(task, "Worker Thread");
        thread.start();
    }
}
```

### yield

```java
public class YieldExample {
    public static void main(String[] args) {
        Runnable task = () -> {
            for (int i = 1; i <= 5; i++) {
                System.out.println(Thread.currentThread().getName() + ": " + i);
                Thread.yield(); // Yield control to other threads
            }
        };

        Thread thread1 = new Thread(task, "Thread 1");
        Thread thread2 = new Thread(task, "Thread 2");

        thread1.start();
        thread2.start();
    }
}
```

### join

```java
public class JoinExample {
    public static void main(String[] args) {
        Runnable task = () -> {
            for (int i = 1; i <= 5; i++) {
                System.out.println(Thread.currentThread().getName() + ": " + i);
                try {
                    Thread.sleep(500); // Pause for 0.5 seconds
                } catch (InterruptedException e) {
                    System.out.println("Thread interrupted");
                }
            }
        };

        Thread thread = new Thread(task, "Worker Thread");
        thread.start();

        try {
            thread.join(); // Wait for the thread to finish
        } catch (InterruptedException e) {
            System.out.println("Main thread interrupted");
        }

        System.out.println("Main thread finished");
    }
}
```

## Inter-Thread Communication
wait, notify, notifyAll

```java
class SharedResource {
    private int value;
    private boolean produced = false;

    public synchronized void produce(int value) {
        while (produced) {
            try {
                wait(); // Wait for the consumer to consume
            } catch (InterruptedException e) {
                System.out.println("Producer interrupted");
            }
        }
        this.value = value;
        System.out.println("Produced: " + value);
        produced = true;
        notify(); // Notify the consumer
    }

    public synchronized void consume() {
        while (!produced) {
            try {
                wait(); // Wait for the producer to produce
            } catch (InterruptedException e) {
                System.out.println("Consumer interrupted");
            }
        }
        System.out.println("Consumed: " + value);
        produced = false;
        notify(); // Notify the producer
    }
}

public class InterThreadCommunicationExample {
    public static void main(String[] args) {
        SharedResource resource = new SharedResource();

        // Producer thread
        Thread producer = new Thread(() -> {
            for (int i = 1; i <= 5; i++) {
                resource.produce(i);
                try {
                    Thread.sleep(1000); // Simulate production time
                } catch (InterruptedException e) {
                    System.out.println("Producer interrupted");
                }
            }
        }, "Producer");

        // Consumer thread
        Thread consumer = new Thread(() -> {
            for (int i = 1; i <= 5; i++) {
                resource.consume();
                try {
                    Thread.sleep(1000); // Simulate consumption time
                } catch (InterruptedException e) {
                    System.out.println("Consumer interrupted");
                }
            }
        }, "Consumer");

        producer.start();
        consumer.start();
    }
}
```

- a. wait - Causes the current thread to wait until another thread calls notify or notifyAll.
- b. notify - Wakes up a single thread that is waiting on the object's monitor.
- c. notifyAll - Wakes up all threads that are waiting on the object's monitor.

**Explanation of Inter-Thread Communication**
- wait: 
	- The producer thread waits if the resource is already produced.
	- The consumer thread waits if the resource is not yet produced.
- notify:
	- The producer notifies the consumer after producing a value.
	- The consumer notifies the producer after consuming a value.
- notifyAll:
	- If multiple threads are waiting, notifyAll wakes up all of them.

**Key Points**
- sleep: Pauses the thread for a specified time.
- yield: Allows other threads to execute.
- join: Waits for a thread to finish.
- wait: Causes the thread to wait until notified.
- notify: Wakes up a single waiting thread.
- notifyAll: Wakes up all waiting threads.

