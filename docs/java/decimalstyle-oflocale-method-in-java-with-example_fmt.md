# Java 中 `DecimalStyle` 类的 `of(Locale)` 方法示例

> 原文：[https://www.geeksforgeeks.org/decimalstyle-oflocale-method-in-java-with-example/](https://www.geeksforgeeks.org/decimalstyle-oflocale-method-in-java-with-example/)

`java.time.format.DecimalStyle` 类的 `of(Locale)` 方法用于获取指定区域设置的 `DecimalStyle` 实例。

## 语法

```java
public static DecimalStyle of(Locale locale)
```

## 参数

该方法接受一个参数 `locale`，表示需要获取其十进制样式的区域设置。

## 返回值

该方法返回指定区域设置的 `DecimalStyle` 实例。

## 异常

这个方法不抛出任何异常。

## 程序示例

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

        Locale locale = new Locale("ENGLISH");

        System.out.println("DecimalStyle for "
                           + locale + " locale: "
                           + ds.of(locale));
    }
}
```

## 输出

```java
DecimalStyle for english locale: DecimalStyle[0+-.]
```

## 参考

[https://docs.oracle.com/javase/10/docs/api/java/time/format/DecimalStyle.html#of(java.util.Locale)](https://docs.oracle.com/javase/10/docs/api/java/time/format/DecimalStyle.html#of(java.util.Locale))