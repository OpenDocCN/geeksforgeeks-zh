# 在 Java 中将 XMLGregorianCalendar 转换为日期

> 原文：[https://www.geeksforgeeks.org/converting-xmlgregoriancalendar-to-date-in-java/](https://www.geeksforgeeks.org/converting-xmlgregoriancalendar-to-date-in-java/)

`XMLGregorianCalendar` 可以根据需要转换为 [`java.util.Date`](https://www.geeksforgeeks.org/date-class-java-examples/) 或 [`java.sql.Date`](https://www.geeksforgeeks.org/how-to-convert-java-sql-date-to-java-util-date-in-java/)。JAXB（Java API for XML Bindings）是从 Java 对象创建 XML 文档和从 Java 对象创建 XML 文件的通用框架。JAXB 还允许根据 XML Schema 文件（`.xsd` 文件）构造 Java 类。默认情况下，JAXB 将 Java 中的 `xs:date`、`xs:time` 和 `xs:dateTime` 映射到 `XMLGregorianCalendar`，但是您可以自定义 XJC 来构造 `java.util.Date` 对象，而不是 `javax.xml.datatype.XMLGregorianCalendar`。

由于 `java.util.Date` 是处理 Java 日期和时间最常用的方法，所以我们总是需要将 `XMLGregorianCalendar` 的实例转换为 Java `Date` 实例。

使用 Java API，我们可以轻松地在 Java 中将 `XMLGregorianCalendar` 转换为 `Date`。

顺便说一下，很高兴地注意到，有三种不同形式的 XML Schema 可以表示日期、时间或两者，而 `java.util.Date` 包含日期和时间的详细信息。

这是一个 Java 程序，它将 `XMLGregorianCalendar` 转换为 `Date`。所以我们将获取 `XMLGregorianCalendar` 并返回 `java.util.Date`。

## 代码

```java
// Convert XMLGregorianCalendar to Date in Java
import java.io.*;
import java.util.*;
import java.util.Date;
import java.util.GregorianCalendar;
import java.util.logging.Level;
import java.util.logging.Logger;
import javax.xml.datatype.DatatypeConfigurationException;
import javax.xml.datatype.DatatypeFactory;
import javax.xml.datatype.XMLGregorianCalendar;

class GFG {
    public static void main(String[] args)
    {
        Date today = new Date();

        // Converting date to XMLGregorianCalendar
        XMLGregorianCalendar xml
            = toXMLGregorianCalendar(today);
        System.out.println(
            "XMLGregorianCalendar from Date in Java      : "
            + xml);

        // Converting XMLGregorianCalendar to java.util.Date
        // in Java
        Date date = toDate(xml);
        System.out.println(
            "java.util.Date from XMLGregorianCalendar in Java : "
            + date);
    }

    public static XMLGregorianCalendar
        toXMLGregorianCalendar(Date date)
    {
        GregorianCalendar gCalendar
            = new GregorianCalendar();
        gCalendar.setTime(date);
        XMLGregorianCalendar xmlCalendar = null;
        try {
            xmlCalendar
                = DatatypeFactory.newInstance()
                      .newXMLGregorianCalendar(gCalendar);
        }
        catch (DatatypeConfigurationException ex) {
            System.out.println(ex);
        }
        return xmlCalendar;
    }

    public static Date toDate(XMLGregorianCalendar calendar)
    {
        if (calendar == null) {
            return null;
        }
        return calendar.toGregorianCalendar().getTime();
    }
}
```

## 输出

```java
XMLGregorianCalendar from Date in Java      : 2021-02-22T17:10:28.732Z
java.util.Date from XMLGregorianCalendar in Java : Mon Feb 22 17:10:28 UTC 2021
```

## 关于 XMLGregorianCalendar 和日期的要点

*   XML Schema 有各种日期、时间和日期时间数据类型，例如 `xsd:date`、`xsd:time` 和 `xsd:dateTime`。默认情况下，JAXB XJC 用于映射到 Java 中的 `XMLGregorianCalendar`。
*   在构造 `GregorianCalendar` 实例时，最好使用构造函数而不是调用 `GregorianCalendar.getInstance()`，因为它类似于 `Calendar.getInstance()`，并且可以根据本地设置返回不同的日历类型，例如泰国本地佛历或日本皇历。使用构造函数时还可以排除类型转换，因为 `getInstance()` 返回的是 `java.util.Calendar` 实例，并防止在 Java 中出现 `ClassCastException`。
*   对于 `xs:date`、`xs:time` 和 `xs:dateTime` 数据类型，可以配置 XJC 生成 `Date` 而不是 `XMLGregorianCalendar`。我稍后会写这个，但这个选项仍然可以探索。

这都是关于如何将 `XMLGregorianCalendar` 转换为 Java `Date` 和 `XMLGregorianCalendar` `Date`。