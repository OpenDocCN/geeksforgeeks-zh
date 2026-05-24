# Java 中的十进制格式符号 getPatternSeparator() 方法示例

> 原文：[https://www.geeksforgeeks.org/decimalformatsymbols-getpatternseparator-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getpatternseparator-method-in-java-with-examples/)

**`getPatternSeparator()`** 方法属于 `java.text.DecimalFormatSymbols` 类，用于获取表示此十进制格式符号区域设置的模式分隔符的字符。此方法返回用于分隔模式中正负子模式的字符。

## 语法

```java
public char getPatternSeparator()
```

## 参数

此方法不接受任何参数。

## 返回值

该方法返回带有区域设置的十进制格式符号的模式分隔符。

## 异常

这个方法不抛出任何异常。

## 程序

```java
// Java program to demonstrate
// the above method

import java.text.*;
import java.util.*;

public class DecimalFormatSymbolsDemo {
    public static void main(String[] args)
    {

        DecimalFormatSymbols dfs
            = new DecimalFormatSymbols();

        System.out.println("Character used "
                           + "for pattern separator: "
                           + dfs.getPatternSeparator());
    }
}
```

## 输出

```java
Character used for pattern separator: ;
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getPatternSeparator--](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getPatternSeparator--)