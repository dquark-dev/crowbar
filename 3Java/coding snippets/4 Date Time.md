## LocalDate Class

```java
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;

public class LocalDateExample {
    public static void main(String[] args) {
        // Get the current date
        LocalDate currentDate = LocalDate.now();
        System.out.println("Current Date: " + currentDate);

        // Create a specific date
        LocalDate specificDate = LocalDate.of(2023, 10, 25);
        System.out.println("Specific Date: " + specificDate);

        // Add days to a date
        LocalDate futureDate = currentDate.plusDays(10);
        System.out.println("Date after 10 days: " + futureDate);

        // Format a date
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("dd/MM/yyyy");
        String formattedDate = currentDate.format(formatter);
        System.out.println("Formatted Date: " + formattedDate);

        // Parse a date from a string
        String dateString = "25/10/2023";
        LocalDate parsedDate = LocalDate.parse(dateString, formatter);
        System.out.println("Parsed Date: " + parsedDate);
    }
}
```

## LocalTime Class

```java
import java.time.LocalTime;
import java.time.format.DateTimeFormatter;

public class LocalTimeExample {
    public static void main(String[] args) {
        // Get the current time
        LocalTime currentTime = LocalTime.now();
        System.out.println("Current Time: " + currentTime);

        // Create a specific time
        LocalTime specificTime = LocalTime.of(15, 30, 45);
        System.out.println("Specific Time: " + specificTime);

        // Add hours to a time
        LocalTime futureTime = currentTime.plusHours(2);
        System.out.println("Time after 2 hours: " + futureTime);

        // Format a time
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("HH:mm:ss");
        String formattedTime = currentTime.format(formatter);
        System.out.println("Formatted Time: " + formattedTime);

        // Parse a time from a string
        String timeString = "15:30:45";
        LocalTime parsedTime = LocalTime.parse(timeString, formatter);
        System.out.println("Parsed Time: " + parsedTime);
    }
}
```

## ZonedDateTime Class

```java
import java.time.ZonedDateTime;
import java.time.ZoneId;
import java.time.format.DateTimeFormatter;

public class ZonedDateTimeExample {
    public static void main(String[] args) {
        // Get the current date and time with a time zone
        ZonedDateTime currentZonedDateTime = ZonedDateTime.now();
        System.out.println("Current Zoned DateTime: " + currentZonedDateTime);

        // Create a specific date and time with a time zone
        ZonedDateTime specificZonedDateTime = ZonedDateTime.of(2023, 10, 25, 15, 30, 45, 0, ZoneId.of("Europe/Paris"));
        System.out.println("Specific Zoned DateTime: " + specificZonedDateTime);

        // Add days to a zoned date-time
        ZonedDateTime futureZonedDateTime = currentZonedDateTime.plusDays(10);
        System.out.println("Zoned DateTime after 10 days: " + futureZonedDateTime);

        // Format a zoned date-time
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm:ss z");
        String formattedZonedDateTime = currentZonedDateTime.format(formatter);
        System.out.println("Formatted Zoned DateTime: " + formattedZonedDateTime);

        // Parse a zoned date-time from a string
        String zonedDateTimeString = "25/10/2023 15:30:45 CEST";
        ZonedDateTime parsedZonedDateTime = ZonedDateTime.parse(zonedDateTimeString, formatter);
        System.out.println("Parsed Zoned DateTime: " + parsedZonedDateTime);
    }
}
```

## Formatting and Parsing

```java
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

public class DateTimeFormatterExample {
    public static void main(String[] args) {
        // Get the current date and time
        LocalDateTime currentDateTime = LocalDateTime.now();
        System.out.println("Current Date and Time: " + currentDateTime);

        // Format the date and time
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm:ss");
        String formattedDateTime = currentDateTime.format(formatter);
        System.out.println("Formatted Date and Time: " + formattedDateTime);

        // Parse a date and time from a string
        String dateTimeString = "25/10/2023 15:30:45";
        LocalDateTime parsedDateTime = LocalDateTime.parse(dateTimeString, formatter);
        System.out.println("Parsed Date and Time: " + parsedDateTime);
    }
}
```

- LocalDate: Represents a date (year, month, day).
- LocalTime: Represents a time (hour, minute, second).
- ZonedDateTime: Represents a date and time with a time zone.
- DateTimeFormatter: Used to format and parse dates, times, and zoned date-times.


