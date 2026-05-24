# Java 中的十进制格式符号 setCurrency()方法，带示例

> 原文:[https://www.geeksforgeeks.org/decimalformatsymbols-setcurrency-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setcurrency-method-in-java-with-examples/)

`setCurrency(Currency currency)` 方法在 `java.text.DecimalFormatSymbols` 类中用于设置此 `DecimalFormatSymbols` 的区域设置的货币。此方法将 `Currency` 作为参数并进行设置。

## 语法

```java
public void setCurrency(Currency currency)
```

## 参数

该方法接受 `Currency` 作为参数，该参数是 `Currency`，将用于表示该十进制格式符号的货币。

## 返回值

此方法不返回任何内容。

## 异常

如果货币为空，该方法抛出 `NullPointerException`。

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

        System.out.println("Current currency: "
                           + dfs.getCurrency());

        Currency currency
            = Currency.getInstance("INR");

        dfs.setCurrency(currency);

        System.out.println("Updated currency: "
                           + dfs.getCurrency());
    }
}
```

## 输出

```java
Current currency: USD
Updated currency: INR
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setCurrency-java.util.Currency-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setCurrency-java.util.Currency-)