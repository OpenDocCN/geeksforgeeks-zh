# 十进制格式符号 Java 中的 setInfinity(字符串)方法示例

> 原文：[https://www.geeksforgeeks.org/decimalformatsymbols-setinfinitystring-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setinfinitystring-method-in-java-with-examples/)

`setInfinity(String)` 方法是 `DecimalFormatSymbols` 类中的一个方法，用于设置表示无穷大的字符串。此方法将表示无穷大的字符串作为参数。

## 语法

```java
public void setInfinity(String infinity)
```

## 参数

该方法接受 `infinity` 作为参数，该参数是将用于表示该十进制格式符号无穷大的字符串。

## 返回值

此方法不返回任何内容。

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

        System.out.println("Current String"
                           + " used for infinity: "
                           + dfs.getInfinity());

        String infinity = "*";

        dfs.setInfinity(infinity);

        System.out.println("Updated String "
                           + "used for infinity: "
                           + dfs.getInfinity());
    }
}
```

## 输出

```java
Current String used for infinity: ?
Updated String used for infinity: *
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setInfinity-java.lang.String-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setInfinity-java.lang.String-)