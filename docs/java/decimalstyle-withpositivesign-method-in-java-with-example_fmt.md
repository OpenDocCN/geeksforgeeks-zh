# 带`withPositiveSign()`方法的十进制样式

> 原文：[https://www.geeksforgeeks.org/decimalstyle-withpositivesign-method-in-java-with-example/](https://www.geeksforgeeks.org/decimalstyle-withpositivesign-method-in-java-with-example/)

Java 中 `java.time.format.DecimalStyle` 类的 `withPositiveSign()` 方法用于设置该 decimal style 的 Locale 中用于表示正号的字符。此方法将字符作为参数，并返回带有更新的正号字符的十进制样式实例。

## 语法

```java
public DecimalStyle withPositiveSign(char positiveSign)
```

## 参数

此方法接受 `positiveSign` 作为参数，该参数是将用于表示此十进制样式的正号的字符。

## 返回值

此方法返回带有更新正号字符的 `DecimalStyle` 实例。

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

        System.out.println(
            "Current Character"
            + " used for positive sign: "
            + ds.getPositiveSign());

        char positiveSign = '*';

        ds = ds.withPositiveSign(positiveSign);

        System.out.println(
            "Updated Character "
            + "used for positive sign: "
            + ds.getPositiveSign());
    }
}
```

## 输出

```java
Current Character used for positive sign: +
Updated Character used for positive sign: *
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/time/format/DecimalStyle.html#withPositiveSign(char)](https://docs.oracle.com/javase/10/docs/api/java/time/format/DecimalStyle.html#withPositiveSign(char))