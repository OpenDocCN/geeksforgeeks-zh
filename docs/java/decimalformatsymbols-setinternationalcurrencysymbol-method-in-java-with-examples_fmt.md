# Java 中的十进制格式符号 setInternationalCurrencySymbol()方法，带示例

> 原文：[https://www.geeksforgeeks.org/decimalformatsymbols-setinternationalcurrencysymbol-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setinternationalcurrencysymbol-method-in-java-with-examples/)

[`java.text`](https://www.geeksforgeeks.org/tag/java-text-package/) 的 [`setInternationalCurrencySymbol(String)`](https://www.geeksforgeeks.org/tag/java-text-package/) 方法。Java 中的 [`DecimalFormatSymbols`](https://www.geeksforgeeks.org/tag/java-text-package/) 类用于设置 ISO 4217 货币代码，该代码用于表示此 [`DecimalFormatSymbols`](https://www.geeksforgeeks.org/tag/java-text-package/) 区域设置的国际货币符号。此方法将表示国际货币符号的字符串作为参数。

## 语法

```java
public void setInternationalCurrencySymbol(
            String internationalCurrencySymbol)
```

## 参数

此方法接受国际货币符号作为参数，该参数是将用于表示此十进制格式符号的国际货币符号的字符串。

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

        System.out.println(
            "Current String used "
            + "for international "
            + "currency symbol: "
            + dfs.getInternationalCurrencySymbol());

        String internationalCurrencySymbol
            = "INR";

        dfs.setInternationalCurrencySymbol(
            internationalCurrencySymbol);

        System.out.println(
            "Updated String used "
            + "for international "
            + "currency symbol: "
            + dfs.getInternationalCurrencySymbol());
    }
}
```

## 输出

```java
Current String used for international currency symbol: USD
Updated String used for international currency symbol: INR
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setInternationalCurrencySymbol-java.lang.String-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setInternationalCurrencySymbol-java.lang.String-)