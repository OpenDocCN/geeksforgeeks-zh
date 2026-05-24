# Java 中的日期格式解析（`String`, `ParsePosition`）方法及示例

> 原文：[https://www.geeksforgeks.org/dateformat-parsestring-parseposition-method-in-java-with-examples/](https://www.geeksforgeks.org/dateformat-parsestring-parseposition-method-in-java-with-examples/)

`DateFormat` 类的 `parse(String the_text, ParsePosition position)` 方法用于从字符串中解析文本以产生日期。该方法从给定的起始索引位置开始分析文本。

**语法：**

```java
public abstract Date parse(String the_text, ParsePosition position)
```

**参数：** 该方法取两个参数：

*   `the_text`：这是 `String` 类型，指的是要解析以产生日期的字符串。
*   `position`：这是 `ParsePosition` 对象类型，指明解析的起始索引信息。

**返回值：** 该方法返回从字符串解析的日期，或者在出现错误时返回空值。

下面的程序说明了 `DateFormat` 类中 `parse()` 方法的工作方式：

**示例 1：**

## Java 代码示例

```java
// Java Code to illustrate parse() method

import java.text.*;
import java.util.Calendar;

public class DateFormat_Demo {
    public static void main(String[] args)
    {
        DateFormat DFormat
            = new SimpleDateFormat("MM/ dd/ yy");

        try {
            Calendar cal = Calendar.getInstance();

            // Use of parse() method to parse
            // Date From String
            String dt = "10/ 27/ 16";
            System.out.println("The unparsed"
                               + " string is: " + dt);

            cal.setTime(DFormat.parse(dt));
            System.out.println("Time parsed: "
                               + cal.getTime());
        }
        catch (ParseException except) {
            except.printStackTrace();
        }
    }
}
```

**输出：**

```java
The unparsed string is: 10/ 27/ 16
Time parsed: Thu Oct 27 00:00:00 UTC 2016
```