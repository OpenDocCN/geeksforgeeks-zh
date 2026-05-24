# Java 中的十进制格式符号集合货币符号(字符串)方法，示例

> 原文: [https://www.geeksforgeeks.org/decimalformatsymbols-setcurrencysymbolstring-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setcurrencysymbolstring-method-in-java-with-examples/)

[`setCurrencySymbol(String)`](https://www.geeksforgeeks.org/tag/java-text-package/) 方法。Java 中的 [`DecimalFormatSymbols`](https://www.geeksforgeeks.org/tag/java-text-package/) 类用于设置字符串，该字符串用于表示该十进制格式符号的区域设置的货币符号。此方法将表示货币符号的字符串作为参数。

## 语法

```java
public void setCurrencySymbol(String currencySymbol)
```

## 参数

此方法接受 `currencySymbol` 作为参数，该参数是将用于表示此十进制格式符号的货币符号的字符串。

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

        System.out.println("Current String used"
            + " for currency symbol: "
            + dfs.getCurrencySymbol());

        String currencySymbol = "*";

        dfs.setCurrencySymbol(currencySymbol);

        System.out.println("Updated String used "
            + "for currency symbol: "
            + dfs.getCurrencySymbol());
    }
}
```

## 输出

```java
Current String used for currency symbol: $
Updated String used for currency symbol: *
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setCurrencySymbol-java.lang.String-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setCurrencySymbol-java.lang.String-)