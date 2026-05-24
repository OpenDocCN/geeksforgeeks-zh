# Java中的`java.nio.file.attribute.FileTime`类

> 原文：[https://www.geeksforgeeks.org/java-nio-file-attribute-filetime-class-in-java/](https://www.geeksforgeeks.org/java-nio-file-attribute-filetime-class-in-java/)

`java.nio.file.attribute.FileTime`类用于获取表示该文件时间戳的值，即该文件上次被修改、访问或创建的时间。

## 类别申报

```java
public final class FileTime
extends Object
implements Comparable<FileTime>
```

## 方法

| 方法 | 描述 |
| --- | --- |
| `compareTo(FileTime other)` | 此方法比较两个`FileTime`对象的值顺序。 |
| `equals(Object object)` | 此方法测试此`FileTime`是否与给定对象相等。 |
| `from(Instant instant)` | 此方法返回一个`FileTime`，表示与提供的`Instant`在时间线上相同的时间点值。 |
| `from(long value, TimeUnit unit)` | 此方法返回一个表示给定粒度单位的值的`FileTime`。 |
| `fromMillis(long value)` | 此方法返回一个表示给定值的`FileTime`（以毫秒为单位）。 |
| `hashCode()` | 此方法计算此`FileTime`的哈希代码。 |
| `to(TimeUnit unit)` | 此方法返回给定粒度单位的值。 |
| `toInstant()` | 此方法将此`FileTime`对象转换为`Instant`。 |
| `toMillis()` | 此方法以毫秒为单位返回值。 |
| `toString()` | 此方法返回此`FileTime`的字符串表示形式。 |

下面是Java中`java.nio.file.attribute.FileTime`类的一些方法的实现：

### Java语言示例

```java
import java.nio.file.attribute.FileTime;
import java.time.Instant;
import java.util.concurrent.TimeUnit;

public class GFG {
    public static void main(String[] args)
    {
        // Variables for storing time values
        long v1 = 21;
        long v2 = 356;

        // Creating an Instant.
        Instant instant
            = Instant.parse("2017-02-03T10:37:30.00Z");

        // Creating FileTime object using from
        // Method This method takes an Integer
        // value and a timeunit as parameters.
        FileTime filetime2
            = FileTime.from(v2, TimeUnit.MILLISECONDS);

        // Creating FileTime object using fromMillis method.
        FileTime filetime1 = FileTime.fromMillis(v1);

        // Creating FileTime object using from Method
        // This method takes an Instant as parameters.
        FileTime filetime3 = FileTime.from(instant);

        // Method to convert this filetime to an instant.
        Instant instantFromFileTime = filetime3.toInstant();

        // Method to convert filetime1 to this timeunit.
        System.out.println(
            filetime1.to(TimeUnit.MILLISECONDS));

        // Method to check if filetime1
        // is equal to filetime2 or not.
        if (filetime1.equals(filetime2))
            System.out.println("FileTime are equal");
        else
            System.out.println("FileTime are not equal");

        // Method to print hashvalue of filetime1.
        System.out.println(filetime1.hashCode());

        // Method to convert filetime1 to milliseconds.
        System.out.println(filetime1.toMillis());

        // Method to comapre filetime1 and filetime2.
        System.out.println(filetime1.compareTo(filetime2));

        // Method to print string
        // representation of filetime1.
        System.out.println(filetime1.toString());
    }
}
```

**输出**

```
FileTime are not equal
1970-01-01T00:00:00.021Z
```