# Java 中的 DateFormatSymbols setShortWeekdays() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/dateformatsymbols-setshortweekdays-method-in-java-with-examples/](https://www.geeksforgeeks.org/dateformatsymbols-setshortweekdays-method-in-java-with-examples/)

Java 中的 `DateFormatSymbols` 类的 `setShortWeekdays(String[] newShWeekds)` 方法用于将字符串格式的日历工作日的短名称设置为一些不同的字符串。例如，“Sun”可以改为“FRI”，“Mon”可以改为“WED”等。

## 语法

```java
public void setShortWeekdays(String[] newShWeekds)
```

## 参数

该方法取一个参数 `newShWeekds` 为 `String` 类型的数组，指的是在已有工作日中需要替换的新字符串。

## 返回值

该方法以字符串格式返回工作日修改后的短名称。

下面的程序说明了 `setShortWeekdays()` 方法的使用。

### 示例 1

```java
// Java code to demonstrate setShortWeekdays()

import java.text.DateFormatSymbols;
import java.util.Locale;

public class DateFormat_Main {
    public static void main(String args[])
    {
        // Initialising DateFormatSymbols object
        DateFormatSymbols format
            = new DateFormatSymbols(
                new Locale("en", "US"));

        // Taking the default short weekdays
        String[] shDays
            = format.getShortWeekdays();

        // Displaying the original
        System.out.print("Original: ");
        for (int i = 1; i < shDays.length; i++) {
            System.out.print(shDays[i] + "  ");
        }
        System.out.println();

        // Taking an alternative names
        String[] modDays = { "WED", "THU", "FRI",
                             "MON", "TUE", "SUN", "SAT" };

        // Setting the default into modified
        format.setShortWeekdays(modDays);

        // Displaying the modified string
        String[] modifiedDays
            = format.getShortWeekdays();

        System.out.print("Modified: ");
        for (int i = 0; i < modifiedDays.length; i++) {
            System.out.print(modifiedDays[i] + "  ");
        }
    }
}
```

**输出：**

```java
Original: Sun  Mon  Tue  Wed  Thu  Fri  Sat  
Modified: WED  THU  FRI  MON  TUE  SUN  SAT
```

### 示例 2

```java
// Java code to demonstrate setShortWeekdays()

import java.text.DateFormatSymbols;
import java.util.Locale;

public class DateFormat_Main {
    public static void main(String args[])
    {
        // Initialising DateFormatSymbols object
        DateFormatSymbols format
            = new DateFormatSymbols(
                new Locale("en", "US"));

        // Taking the default short weekdays
        String[] shDays = format.getShortWeekdays();

        // Displaying the original
        System.out.print("Original: ");
        for (int i = 1; i < shDays.length; i++) {
            System.out.print(shDays[i] + "  ");
        }
        System.out.println();

        // Taking an alternative names with
        // additional random strings
        String[] modDays = { "WED", "THU", "FRI",
                             "MON", "TUE", "SUN",
                             "SAT", "ONE", "TWO" };

        // Setting the default into modified
        format.setShortWeekdays(modDays);

        // Displaying the modified string
        String[] modifiedDays
            = format.getShortWeekdays();

        System.out.print("Modified: ");
        for (int i = 0; i < modifiedDays.length; i++) {
            System.out.print(modifiedDays[i] + "  ");
        }
    }
}
```

**输出：**

```java
Original: Sun  Mon  Tue  Wed  Thu  Fri  Sat  
Modified: WED  THU  FRI  MON  TUE  SUN  SAT  ONE  TWO
```

## 参考

[https://docs.oracle.com/javase/8/docs/api/java/text/DateFormatSymbols.html#setShortWeekdays-java.lang.String:A-](https://docs.oracle.com/javase/8/docs/api/java/text/DateFormatSymbols.html#setShortWeekdays-java.lang.String:A-)