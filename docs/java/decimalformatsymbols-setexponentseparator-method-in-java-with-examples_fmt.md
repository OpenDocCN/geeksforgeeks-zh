# Java中的DecimalFormatSymbols.setExponentSeparator()方法示例

> 原文：[https://www.geeksforgeeks.org/decimalformatsymbols-setexponentseparator-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setexponentseparator-method-in-java-with-examples/)

## 方法描述

`DecimalFormatSymbols`类中的`setExponentSeparator(String)`方法用于设置表示此`DecimalFormatSymbols`对象所对应区域设置的指数分隔符的字符串。此方法接受一个表示指数分隔符的字符串作为参数。

## 语法

```java
public void setExponentSeparator(String exponentSeparator)
```

## 参数

此方法接受一个`String`类型的参数`exponentSeparator`，该参数是将用于表示此`DecimalFormatSymbols`对象的指数分隔符的字符串。

## 返回值

此方法不返回任何内容（返回类型为`void`）。

## 异常

此方法不抛出任何异常。

## 示例程序

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

        System.out.println("Current String used "
            + "for exponent separator: "
            + dfs.getExponentSeparator());

        String exponentSeparator = "*";

        dfs.setExponentSeparator(exponentSeparator);

        System.out.println("Updated String used for"
            + " exponent separator: "
            + dfs.getExponentSeparator());
    }
}
```

## 输出

```java
Current String used for exponent separator: E
Updated String used for exponent separator: *
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setExponentSeparator-java.lang.String-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#setExponentSeparator-java.lang.String-)