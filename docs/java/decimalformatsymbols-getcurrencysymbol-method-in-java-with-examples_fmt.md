# Java 中的抽取格式符号 `getCurrencySymbol()` 方法，带示例

> 原文：[https://www.geeksforgeeks.org/decimalformatsymbols-getcurrencysymbol-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getcurrencysymbol-method-in-java-with-examples/)

`DecimalFormatSymbols` 类中的 `getCurrencySymbol()` 方法用于获取表示该 `DecimalFormatSymbols` 对象所关联区域设置的货币符号的字符串。此方法返回该地区货币符号的字符串。

## 语法：
```java
public String getCurrencySymbol()
```

## 参数：
此方法不接受任何参数。

## 返回值：
这个方法返回一个 `DecimalFormatSymbols` 的货币符号，默认区域设置。

## 异常：
这个方法不抛出任何异常。

## 程序：
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

        System.out.println("Character used"
            + " for currency symbol: "
            + dfs.getCurrencySymbol());
    }
}
```

## 输出：
```java
Character used for currency symbol: $
```

## 参考：
[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getCurrencySymbol--](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getCurrencySymbol--)