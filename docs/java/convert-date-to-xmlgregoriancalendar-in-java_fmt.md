# 将日期转换为 Java 中的 XMLGregorianCalendar

> 原文：[https://www.geeksforgeeks.org/convert-date-to-xmlgregoriancalendar-in-java/](https://www.geeksforgeeks.org/convert-date-to-xmlgregoriancalendar-in-java/)

`XMLGregorianCalendar`：在 `XML Schema` 标准中定义了以 XML 格式指定日期的规则。Java 1.5 中引入的 `XMLGregorianCalendar` 类是 W3C XML Schema 1.0 日期/时间数据类型的表示，需要使用 XML 格式。

在这种方法中，我们首先将标准日期更改为 `GregorianCalendar` 日期格式，然后使用 `DatatypeFactory.newXMLGregorianCalendar()` 方法将其更改为 `XMLGregorianCalendar` 日期。`DatatypeFactory.newInstance()` 方法用于创建新的工厂实例，该工厂可以将 XML 类型映射到 Java 对象或从 Java 对象映射到 XML 类型。

## Java 代码示例

```java
// Java program to Convert Date to XMLGregorianCalendar

// importing necessary packages
import java.util.Date;
import java.util.GregorianCalendar;
import javax.xml.datatype.DatatypeFactory;
import javax.xml.datatype.XMLGregorianCalendar;

public class DateToXMLGregorianCalendar {

    public static void main(String[] args) {

        // Create Date Object
        Date current_date = new Date();

        // current date time in standard format
        System.out.println("Standard Format :- " + current_date);

        XMLGregorianCalendar xmlDate = null;

        // Gregorian Calendar object creation
        GregorianCalendar gc = new GregorianCalendar();

        // giving current date and time to gc
        gc.setTime(current_date);

        try {
            xmlDate = DatatypeFactory.newInstance()
                          .newXMLGregorianCalendar(gc);
        } catch (Exception e) {
            e.printStackTrace();
        }

        // current date time in XMLGregorianCalendar format
        System.out.println("XMLGregorianCalendar Format :- " + xmlDate);
    }
}
```

**输出**

```java
Standard Format :- Tue Feb 16 17:44:25 UTC 2021
XMLGregorianCalendar Format :- 2021-02-16T17:44:25.164Z
```