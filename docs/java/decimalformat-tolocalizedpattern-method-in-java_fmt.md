# Java中的`DecimalFormat` `toLocalizedPattern()`方法

> 原文：[https://www.geeksforgeeks.org/decimalformat-tolocalizedpattern-method-in-java/](https://www.geeksforgeeks.org/decimalformat-tolocalizedpattern-method-in-java/)

Java中的`DecimalFormat`类的`toLocalizedPattern()`方法用于将该`DecimalFormat`的当前模式的格式转换为本地化的字符串格式。这个转换后的本地化字符串表示用于格式化这个`DecimalFormat`实例的当前状态的模式。

**语法**：
```java
public String toLocalizedPattern()
```

**参数**：该方法不接受任何参数。

**返回值**：该方法返回一个本地化字符串，该字符串表示用于格式化该`DecimalFormat`实例的当前状态的模式。

下面的程序说明了上述方法：

**程序1**：
```java
// Java program to illustrate the
// toLocalizedPattern() method

import java.text.DecimalFormat;

public class GFG {

    public static void main(String[] args)
    {
        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Convert the current formatting state
        // to a string object
        String pattern = deciFormat.toLocalizedPattern();

        System.out.println(pattern);
    }
}
```

**输出**：
```java
#,##0.###
```

**程序2**：
```java
// Java program to illustrate the
// toLocalizedPattern() method

import java.text.DecimalFormat;

public class GFG {

    public static void main(String[] args)
    {
        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Apply a new pattern
        deciFormat.applyPattern("##,##.##");

        // Convert the current formatting state
        // to a string object
        String pattern = deciFormat.toLocalizedPattern();

        System.out.println(pattern);
    }
}
```

**输出**：
```java
#,##0.##;#,##0.##
```

**参考**：[https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#toLocalizedPattern()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#toLocalizedPattern())