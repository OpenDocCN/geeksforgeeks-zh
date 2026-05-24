# 十进制格式符号 Java 中的 `setNaN(String)` 方法示例

> 原文：[https://www.geeksforgeeks.org/decimalformatsymbols-setnanstring-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setnanstring-method-in-java-with-examples/)

`setNaN(String)` 方法是 Java 中 `DecimalFormatSymbols` 类的一部分，用于设置表示此 `DecimalFormatSymbols` 区域设置的 NaN 的字符串。此方法将用于表示 NaN 的字符串作为参数。

## 语法

```java
public void setNaN(String NaN)
```

## 参数

该方法接受 `NaN` 作为参数，该参数是将用于表示此 `DecimalFormatSymbols` 的 NaN 的字符串。

## 返回值

此方法不返回任何内容。

## 异常

此方法不抛出任何异常。

## 程序示例

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

        System.out.println("Current String "
                           + "used for NaN: "
                           + dfs.getNaN());

        String NaN = "*";

        dfs.setNaN(NaN);

        System.out.println("Updated String "
                           + "used for NaN: "
                           + dfs.getNaN());
    }
}
```

## 输出

```java
Current String used for NaN: ?
Updated String used for NaN: *
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setNaN-java.lang.String-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setNaN-java.lang.String-)