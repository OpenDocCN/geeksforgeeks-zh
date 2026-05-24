# Java 中的 `DecimalStyle` `getNegativeSign()` 方法示例

> 原文：[https://www.geeksforgeeks.org/decimalstyle-getnegativesign-method-in-java-with-example/](https://www.geeksforgeeks.org/decimalstyle-getnegativesign-method-in-java-with-example/)

`java.time.format.DecimalStyle` 类的 `getNegativeSign()` 方法用于获取用于表示该 `DecimalStyle` 的 `Locale` 负号的字符。此方法返回该区域设置的负号字符。

## 语法

```java
public char getNegativeSign()
```

## 参数

此方法不接受任何参数。

## 返回值

这个方法返回一个 `char`，代表这个十进制样式的负号。

## 异常

这个方法不抛出任何异常。

## 程序

```java
// Java program to demonstrate
// the above method

import java.time.format.*;
import java.util.*;

public class DecimalStyleDemo {
    public static void main(String[] args)
    {

        DecimalStyle ds
            = DecimalStyle.STANDARD;

        System.out.println("Character used "
                           + "for negative sign: "
                           + ds.getNegativeSign());
    }
}
```

## 输出

```
Character used for negative sign: -
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/time/format/DecimalStyle.html#getNegativeSign()](https://docs.oracle.com/javase/10/docs/api/java/time/format/DecimalStyle.html#getNegativeSign())