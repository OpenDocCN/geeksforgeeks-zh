# 在 Java 中将字符串转换为日期

> 原文: [https://www.geeksforgeeks.org/convert-string-to-date-in-java/](https://www.geeksforgeeks.org/convert-string-to-date-in-java/)

给定日期格式的字符串，任务是将该字符串转换为实际日期。这里的主要概念是 `parse()` 方法，它有助于转换。

插图:

```java
Input : string = "2018-10-28T15:23:01Z"
Output: 2018-10-28T15:23:01Z

Input : string = "28 October, 2018"
Output: 2018-10-28
```

**方法:**

1.  使用 `Instant` 类
2.  使用 `DateTimeFormatter` 类
3.  使用 `SimpleDateFormat` 类

现在让我们讨论一下

## 方法 1: 使用 Instant 类

`java.time` 包中的 `Instant` 类给出纳秒精度。它类似于 `Date` 类，但精度更高。

**进场:**

1.  获取要转换的字符串。
2.  创建一个空的 `Instant` 时间戳对象
3.  使用 `Instant.parse()` 方法将字符串转换为日期。
4.  如果转换成功，则打印日期
5.  如果转换不成功，则会引发 `DateTimeParseException`。

**示例:**

```java
// Java Program to Convert String to Date

// Importing required classes
import java.time.Instant;
import java.time.format.DateTimeParseException;

// Main class
class GFG {

    // Method to convert String to Date
    public static Instant getDateFromString(String string)
    {
        // Creating an instant object
        Instant timestamp = null;

        // Parsing the string to Date
        timestamp = Instant.parse(string);

        // Returning the converted timestamp
        return timestamp;
    }

    // Main driver method
    public static void main(String[] args)
    {
        // Getting the string
        String string = "2018-10-28T15:23:01Z";

        // Try block to check for exceptions
        try {

            // Getting the Date from String by
            // creating object of Instant class
            Instant timestamp = getDateFromString(string);

            // Printing the converted date
            System.out.println(timestamp);
        }

        // Catch block to handle exceptions
        catch (DateTimeParseException e) {

            // Throws DateTimeParseException
            // if the string cannot be parsed
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
2018-10-28T15:23:01Z
```

## 方法 2: 使用 DateTimeFormatter 类

**进场:**

1.  获取要转换的字符串和所需的格式。
2.  创建一个空的 `LocalDate` 对象
3.  使用 `LocalDate.parse()` 方法将字符串转换为日期。
4.  如果转换成功，则打印日期
5.  如果字符串模式无效，则会引发 `IllegalArgumentException`。
6.  如果转换不成功，则会引发 `DateTimeParseException`。

**例**

```java
// Java program to convert String to Date

// Importing required classes
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;
import java.time.format.DateTimeParseException;

// Main class
class GFG {

    // Method 1 to convert String to Date
    public static LocalDate
    getDateFromString(String string,
                      DateTimeFormatter format)
    {

        // Converting the string to date
        // in the specified format
        LocalDate date = LocalDate.parse(string, format);

        // Returning the converted date
        return date;
    }

    // Method 2: Main driver method
    public static void main(String[] args)
    {
        // Getting the custom string input
        String string = "28 October, 2018";

        // Getting the format by creating an object of
        // DateTimeFormatter class
        DateTimeFormatter format
            = DateTimeFormatter.ofPattern("d MMMM, yyyy");

        // Try block to check for exceptions
        try {

            // Getting the Date from String
            LocalDate date
                = getDateFromString(string, format);

            // Printing the converted date
            System.out.println(date);
        }

        // Catch block to handle exceptions occurring
        // if the String pattern is invalid
        catch (IllegalArgumentException e) {

            // Display the exception
            System.out.println("Exception: " + e);
        }

        // If the String was unable to be parsed
        catch (DateTimeParseException e) {

            // Display the exception
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
2018-10-28
```

## 方法 3: 使用 SimpleDateFormat 类

**程序:**

1.  获取字符串输入并将其存储到字符串中
2.  参照 `SimpleDateFormat` 类创建 `Date` 类的对象
3.  将日期格式解析到其中。
4.  打印相应的日期。

**例**

```java
// Java Program to Convert String to Date

// Importing required classes
import java.text.SimpleDateFormat;
import java.util.Date;

// Main class
class GFG {

    // main driver method
    public static void main(String[] args) throws Exception
    {

        // Custom string as input
        String strDate = "29/12/96";

        // Creating an object of Date class with reference
        // to SimpleDateFormat class and
        // lately parsing the above string into it
        Date date = new SimpleDateFormat("dd/mm/yyyy")
                        .parse(strDate);

        // Print and display the date corresponding to
        // above input string
        System.out.print(strDate + " " + date);
    }
}
```

**输出:**

![](img/7fe81414557162a7b7397c9a33a830e9.png)