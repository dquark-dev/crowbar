
## Exception Handling

```java
public class ExceptionHandlingExample {
    public static void main(String[] args) {
        try {
            int result = divide(10, 0); // This will throw an ArithmeticException
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Error: " + e.getMessage()); // Handle the exception
        } finally {
            System.out.println("This block will always execute.");
        }
    }

    public static int divide(int a, int b) {
        if (b == 0) {
            throw new ArithmeticException("Division by zero is not allowed.");
        }
        return a / b;
    }
}
```

## Custom Exception

```java
// Custom exception class
class InsufficientFundsException extends Exception {
    public InsufficientFundsException(String message) {
        super(message);
    }
}

public class CustomExceptionExample {
    public static void main(String[] args) {
        try {
            withdraw(100, 50); // This will not throw an exception
            withdraw(100, 150); // This will throw an InsufficientFundsException
        } catch (InsufficientFundsException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }

    public static void withdraw(double balance, double amount) throws InsufficientFundsException {
        if (amount > balance) {
            throw new InsufficientFundsException("Insufficient funds. You are short by: " + (amount - balance));
        }
        System.out.println("Withdrawal successful. Remaining balance: " + (balance - amount));
    }
}
```

## Using Multiple Catch Blocks

```java
public class MultipleCatchExample {
    public static void main(String[] args) {
        try {
            int[] numbers = {1, 2, 3};
            System.out.println(numbers[5]); // This will throw an ArrayIndexOutOfBoundsException
            int result = divide(10, 0); // This will throw an ArithmeticException
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array Index Error: " + e.getMessage());
        } catch (ArithmeticException e) {
            System.out.println("Arithmetic Error: " + e.getMessage());
        } finally {
            System.out.println("This block will always execute.");
        }
    }

    public static int divide(int a, int b) {
        if (b == 0) {
            throw new ArithmeticException("Division by zero is not allowed.");
        }
        return a / b;
    }
}
```

## Throwing Exceptions

```java
public class ThrowExample {
    public static void main(String[] args) {
        try {
            checkAge(15); // This will throw an exception
        } catch (ArithmeticException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }

    public static void checkAge(int age) {
        if (age < 18) {
            throw new ArithmeticException("Access denied - You must be at least 18 years old.");
        } else {
            System.out.println("Access granted - You are old enough.");
        }
    }
}
```

Summary of Exception Handling
- try: Contains code that might throw an exception.
- catch: Handles the exception.
- finally: Executes code regardless of whether an exception is thrown.
- throw: Explicitly throws an exception.
- Custom Exceptions: Create your own exceptions by extending Exception or RuntimeException

## Checked Exceptions

```java
// Custom checked exception
class InsufficientFundsException extends Exception {
    public InsufficientFundsException(String message) {
        super(message);
    }
}

public class CustomCheckedExceptionExample {
    public static void main(String[] args) {
        try {
            withdraw(100, 150); // This will throw InsufficientFundsException
        } catch (InsufficientFundsException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }

    // Method that throws a custom checked exception
    public static void withdraw(double balance, double amount) throws InsufficientFundsException {
        if (amount > balance) {
            throw new InsufficientFundsException("Insufficient funds. You are short by: " + (amount - balance));
        }
        System.out.println("Withdrawal successful. Remaining balance: " + (balance - amount));
    }
}
```

## Unchecked Exception

```java
// Custom unchecked exception
class InvalidInputException extends RuntimeException {
    public InvalidInputException(String message) {
        super(message);
    }
}

public class CustomUncheckedExceptionExample {
    public static void main(String[] args) {
        try {
            validateInput(""); // This will throw InvalidInputException
        } catch (InvalidInputException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }

    // Method that throws a custom unchecked exception
    public static void validateInput(String input) {
        if (input == null || input.isEmpty()) {
            throw new InvalidInputException("Input cannot be null or empty.");
        }
        System.out.println("Input is valid: " + input);
    }
}
```

