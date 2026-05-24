# Java 中的十进制格式符号设置百分比(字符)方法，示例

> 原文: [https://www.geeksforgeeks.org/decimalformatsymbols-setpercentchar-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setpercentchar-method-in-java-with-examples/)

`DecimalFormatSymbols` 类的 `setPercent(char)` 方法用于设置用于表示此十进制格式符号区域设置百分号的字符。此方法将表示百分号的字符作为参数。

## 语法

```java
public void setPercent(char percent)
```

## 参数

此方法接受 `percent` 作为参数，该参数是将用于表示此十进制格式符号的百分比符号的字符。

## 返回值

此方法不返回任何内容。

## 异常

此方法不抛出任何异常。

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

        System.out.println("Current Character used"
                           + " for percent sign: "
                           + dfs.getPercent());

        char percent = '*';

        dfs.setPercent(percent);

        System.out.println("Updated Character used"
                           + " for percent sign: "
                           + dfs.getPercent());
    }
}
```

## 输出

```java
Current Character used for percent sign: %
Updated Character used for percent sign: *
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setPercent-char-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setPercent-char-)