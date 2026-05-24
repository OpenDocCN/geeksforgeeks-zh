# Java 中的日期格式类

> 原文:[https://www.geeksforgeeks.org/dateformat-class-in-java/](https://www.geeksforgeeks.org/dateformat-class-in-java/)

`java.text.DateFormat` 是一个抽象类，用于格式化和解析任何地区的日期。它允许我们将日期格式化为文本，并将文本解析为日期。`DateFormat` 类提供了许多获取、格式化、解析默认日期/时间的功能。

`DateFormat` 类扩展了 `Format` 类，这意味着它是 `Format` 类的子类。由于 `DateFormat` 类是一个抽象类，因此，它可以用于日期/时间格式化子类，这些子类以独立于语言的方式格式化和解析日期或时间。

**类签名:**

```java
public abstract class DateFormat extends Format
```

### 构造器

`DateFormat()`: `DateFormat()` 是 `DateFormat` 类的构造函数，在创建 `DateFormat` 类的对象实例时调用。

> **注意:** `DateFormat` 是一个抽象类，因此不能实例化。

### 日期格式中的字段

<figure class="table">

| 序号 | 字段 | 数据类型 |
| --- | --- | --- |
| 1. | `AM_PM_FIELD` | 静态整数 |
| 2. | `calendar` | 受保护的日历 |
| 3. | `DATE_FIELD` | 静态整数 |
| 4. | `DAY_OF_WEEK_FIELD` | 静态整数 |
| 5. | `DAY_OF_WEEK_IN_MONTH_FIELD` | 静态整数 |
| 6. | `DAY_OF_YEAR_FIELD` | 静态整数 |
| 7. | `DEFAULT` | 静态整数 |
| 8. | `ERA_FIELD` | 静态整数 |
| 9. | `FULL` | 静态整数 |
| 10. | `HOUR_OF_DAY0_FIELD` | 静态整数 |
| 11. | `HOUR_OF_DAY1_FIELD` | 静态整数 |
| 12. | `HOUR0_FIELD` | 静态整数 |
| 13. | `HOUR1_FIELD` | 静态整数 |
| 14. | `LONG` | 静态整数 |
| 15. | `MEDIUM` | 静态整数 |
| 16. | `MILLISECOND_FIELD` | 静态整数 |
| 17. | `MINUTE_FIELD` | 静态整数 |
| 18. | `MONTH_FIELD` | 静态整数 |
| 19. | `numberFormat` | 受保护的数字格式 |
| 20. | `SECOND_FIELD` | 静态整数 |
| 21. | `SHORT` | 静态整数 |
| 22. | `TIMEZONE_FIELD` | 静态整数 |
| 23. | `WEEK_OF_MONTH_FIELD` | 静态整数 |
| 24. | `WEEK_OF_YEAR_FIELD` | 静态整数 |
| 25. | `YEAR_FIELD` | 静态整数 |

</figure>

### 日期格式类的方法

<figure class="table">

| 序号 | 方法 | 描述 | 返回类型 |
| --- | --- | --- | --- |
| 1. | [`format(Date date)`](https://www.geeksforgeeks.org/dateformat-format-method-in-java-with-examples/) | 此方法将日期格式化为日期/时间字符串 | `String` |
| 2. | `format(Date, StringBuffer toappendto, FieldPosition)` | 此方法将日期格式化为日期/时间字符串。 | `StringBuffer` |
| 3. | [`getCalendar()`](https://www.geeksforgeeks.org/dateformat-getcalendar-method-in-java-with-examples/) | 此方法返回与此日期/时间格式化程序关联的日历 | `Calendar` |
| 4. | [`getDateInstance()`](https://www.geeksforgeeks.org/dateformat-getdateinstance-method-in-java-with-examples/) | 此方法返回具有默认区域设置的默认格式样式的日期格式化程序 | 静态 `DateFormat` |
| 5. | `getDateInstance(int style)` | 此方法返回具有给定区域设置的给定格式样式的日期格式化程序。 | 静态 `DateFormat` |
| 6. | `getDateTimeInstance()` | 此方法返回具有默认区域设置的默认格式样式的日期/时间格式化程序。 | 静态 `DateFormat` |
| 7. | `getDateTimeInstance(int dateStyle, int timeStyle)` | 此方法返回具有默认区域设置的给定日期和时间格式样式的日期/时间格式化程序 | 静态 `DateFormat` |
| 8. | `getInstance()` | 此方法返回默认日期/时间格式化程序，该格式化程序对日期和时间都使用 `SHORT` 样式。 | 静态 `DateFormat` |
| 9. | [`getTimeInstance()`](https://www.geeksforgeeks.org/dateformat-gettimeinstance-method-in-java-with-examples/) | 此方法返回具有默认区域设置的默认格式样式的时间格式化程序。 | 静态 `DateFormat` |
| 10. | `getTimeInstance(int style)` | 此方法返回具有默认区域设置的给定格式样式的时间格式化程序。 | 静态 `DateFormat` |
| 11. | `getTimeInstance(int style, Locale alocale)` | 此方法返回具有给定区域设置的给定格式样式的时间格式化程序。 | 静态 `DateFormat` |
| 12. | `getNumberFormat()` | 此方法返回格式化的数字，日期/时间格式化程序使用该数字来格式化和分析时间。 | `NumberFormat` |
| 13. | `parse(String source)` | 此方法从给定字符串的开头分析文本以生成日期。 | `Date` |
| 14. | [`parse(String source, ParsePosition pos)`](https://www.geeksforgeeks.org/dateformat-parsestring-parseposition-method-in-java-with-examples/) | 此方法根据给定的分析位置分析日期/时间字符串。 | `Date` |
| 15. | `parseObject(String source, ParsePosition pos)` | 此方法分析字符串中的文本以生成日期。 | `Object` |
| 16. | [`setCalendar(Calendar calendar)`](https://www.geeksforgeeks.org/dateformat-setcalendar-method-in-java-with-examples/) | 此方法设置此日期格式使用的日历。 | `void` |
| 17. | [`setLenient(boolean lenient)`](https://www.geeksforgeeks.org/dateformat-setlenient-method-in-java-with-examples/) | 此方法指定日期/时间解析是否宽松。 | `void` |
| 18. | [`setTimeZone(TimeZone)`](https://www.geeksforgeeks.org/dateformat-settimezone-method-in-java-with-examples/) | 此方法设置此日期格式对象的日历的时区。 | `void` |
| 19. | [`getTimeZone()`](https://www.geeksforgeeks.org/dateformat-gettimezone-method-in-java-with-examples/) | 此方法返回时区 | `TimeZone` |

</figure>

**示例:** Java 程序，用于更好地理解 `DateFormat` 类

## 示例代码

```java
// import java.text package for using DateFormat class
import java.text.*;
import java.util.*;
class GFG {
    public static void main(String[] args)
    {
        // create instance of Date class
        Date date = new Date();
        // to format a date for our timezone
        System.out.println(
            "Local Date and Time is : "
            + DateFormat.getInstance().format(date));

        // to format a date for different locale
        System.out.println(
            "Date of Canada region : "
            + DateFormat
                  .getDateInstance(DateFormat.LONG,
                                   Locale.CANADA)
                  .format(date));
        System.out.println(
            "Time of Canada region : "
            + DateFormat
                  .getTimeInstance(DateFormat.LONG,
                                   Locale.CANADA)
                  .format(date));
        System.out.println(
            "Date of Italy region : "
            + DateFormat
                  .getDateInstance(DateFormat.LONG,
                                   Locale.ITALY)
                  .format(date));
        System.out.println(
            "Time of Italy region : "
            + DateFormat
                  .getTimeInstance(DateFormat.LONG,
                                   Locale.ITALY)
                  .format(date));

        // to get the time zone
        System.out.println(
            "Time zone is : "
            + DateFormat.getInstance().getTimeZone());
        System.out.println(
            "Local Date and Time using getDateInstance() : "
            + DateFormat.getDateInstance().format(date));
        System.out.println(
            "Local Date and Time using getTimeInstance() : "
            + DateFormat.getTimeInstance().format(date));
        System.out.println(
            "Local Date and Time using getDateTimeInstance() : "
            + DateFormat.getDateTimeInstance().format(
                date));
        System.out.println(
            "Local Date and Time using getDateInstance(DateFormat.LONG) : "
            + DateFormat.getTimeInstance(DateFormat.LONG)
                  .format(date));
        System.out.println(
            "Local Date and Time using getDateInstance(DateFormat.MEDIUM) : "
            + DateFormat.getTimeInstance(DateFormat.MEDIUM)
                  .format(date));
        System.out.println(
            "Local Date and Time using getDateInstance(DateFormat.SHORT) : "
            + DateFormat.getTimeInstance(DateFormat.SHORT)
                  .format(date));
    }
}
```

**输出**

```java
Local Date and Time is : 11/28/21, 7:17 PM
Date of Canada region : November 28, 2021
Time of Canada region : 7:17:40 p.m. UTC
Date of Italy region : 28 novembre 2021
Time of Italy region : 19:17:40 UTC
Time zone is : sun.util.calendar.ZoneInfo[id="Etc/UTC",offset=0,dstSavings=0,useDaylight=false,transitions=0,lastRule=null]
Local Date and Time using getDateInstance() : Nov 28, 2021
Local Date and Time using getTimeInstance() : 7:17:40 PM
Local Date and Time using getDateTimeInstance() : Nov 28, 2021, 7:17:40 PM
Local Date and Time using getDateInstance(DateFormat.LONG) : 7:17:40 PM UTC
Local Date and Time using getDateInstance(DateFormat.MEDIUM) : 7:17:40 PM
Local Date and Time using getDateInstance(DateFormat.SHORT) : 7:17 PM
```