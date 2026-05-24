# Java 中的 Month getDisplayName()方法

> 原文：[https://www.geeksforgeeks.org/month-getdisplayname-method-in-java/](https://www.geeksforgeeks.org/month-getdisplayname-method-in-java/)

`getDisplayName()` 方法是 `Month` 枚举的内置方法，用于获取这个 `Month` 实例指定的年月的文本表示。

## 语法

```java
public String getDisplayName(TextStyle style,
                             Locale locale)
```

## 参数

该方法接受如下所述的两个参数：

*   `style`：此参数指定要使用的文本样式或长度，例如 short、long 等。
*   `locale`：此参数指定要使用的区域设置。

## 返回值

该方法返回本月实例指定月份的文本表示。

下面的程序说明了上述方法：

**程序 1**：

```java
import java.time.*;
import java.time.Month;
import java.time.format.TextStyle;
import java.util.Locale;

class monthEnum {
    public static void main(String[] args)
    {
        // Create a month instance
        Month month = Month.of(3);

        // Generate textual representation
        System.out.println(month.getDisplayName(TextStyle.SHORT,
                                                Locale.ENGLISH));
    }
}
```

**输出：**

```java
Mar
```

**程序 2**：

```java
import java.time.*;
import java.time.Month;
import java.time.format.TextStyle;
import java.util.Locale;

class monthEnum {
    public static void main(String[] args)
    {
        // Create a month instance
        Month month = Month.of(12);

        // Generate textual representation
        System.out.println(month.getDisplayName(TextStyle.SHORT,
                                                Locale.ENGLISH));
    }
}
```

**输出：**

```java
Dec
```

**参考**：[https://docs.oracle.com/javase/8/docs/api/java/time/Month.html#getDisplayName-java.time.format.TextStyle-java.util.Locale-](https://docs.oracle.com/javase/8/docs/api/java/time/Month.html#getDisplayName-java.time.format.TextStyle-java.util.Locale-)