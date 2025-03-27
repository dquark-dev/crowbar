 
## While loop
```java
public class WhileLoopExample {
    public static void main(String[] args) {
        int i = 1; // Initialize loop variable

        while (i <= 5) { // Condition
            System.out.println("Number: " + i);
            i++; // Update loop variable
        }
    }
}
```

## Do…while loop

```java
 public class DoWhileLoopExample {
    public static void main(String[] args) {
        int i = 1; // Initialize loop variable

        do {
            System.out.println("Number: " + i);
            i++; // Update loop variable
        } while (i <= 5); // Condition
    }
}
```

## For loop

```java
public class ForLoopExample {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            System.out.println("Number: " + i);
        }
    }
}
```

### for each loop

```java
public class ForEachLoopExample {
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 40, 50};

        for (int number : numbers) {
            System.out.println("Number: " + number);
        }
    }
}
```

## if statement

```java
public class IfElseExample {
    public static void main(String[] args) {
        int number = -5;

        if (number > 0) {
            System.out.println("The number is positive.");
        } else {
            System.out.println("The number is not positive.");
        }
    }
}
```
## if…else statement
```java
public class IfElseIfExample {
    public static void main(String[] args) {
        int number = 0;

        if (number > 0) {
            System.out.println("The number is positive.");
        } else if (number < 0) {
            System.out.println("The number is negative.");
        } else {
            System.out.println("The number is zero.");
        }
    }
}
```

### ternary operators

```java
public class TernaryOperatorExample {
    public static void main(String[] args) {
        int number = 10;
        String result = (number > 0) ? "Positive" : "Not Positive";
        System.out.println("The number is " + result);
    }
}
```
## switch statement

```java
public class SwitchExample {
    public static void main(String[] args) {
        int day = 3; // 1 = Monday, 2 = Tuesday, ..., 7 = Sunday

        switch (day) {
            case 1:
                System.out.println("Monday");
                break;
            case 2:
                System.out.println("Tuesday");
                break;
            case 3:
                System.out.println("Wednesday");
                break;
            case 4:
                System.out.println("Thursday");
                break;
            case 5:
                System.out.println("Friday");
                break;
            case 6:
                System.out.println("Saturday");
                break;
            case 7:
                System.out.println("Sunday");
                break;
            default:
                System.out.println("Invalid day");
        }
    }
}
```

```java
public class SwitchStringExample {
    public static void main(String[] args) {
        String fruit = "Apple";

        switch (fruit) {
            case "Apple":
                System.out.println("It's an apple.");
                break;
            case "Banana":
                System.out.println("It's a banana.");
                break;
            case "Cherry":
                System.out.println("It's a cherry.");
                break;
            default:
                System.out.println("Unknown fruit.");
        }
    }
}
```

```java
enum Day {
    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY
}

public class SwitchEnumExample {
    public static void main(String[] args) {
        Day day = Day.WEDNESDAY;

        switch (day) {
            case MONDAY:
                System.out.println("Start of the work week.");
                break;
            case WEDNESDAY:
                System.out.println("Midweek.");
                break;
            case FRIDAY:
                System.out.println("End of the work week.");
                break;
            default:
                System.out.println("Some other day.");
        }
    }
}
```

