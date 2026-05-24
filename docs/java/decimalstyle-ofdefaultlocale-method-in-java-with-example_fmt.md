# Java 中的 `DecimalStyle` `ofDefaultLocale()` 方法示例

> 原文：`https://www.geeksforgeeks.org/decimalstyle-ofdefaultlocale-method-in-java-with-example/`

`java.time.format.DecimalStyle` 类的 `ofDefaultLocale()` 方法用于获取默认 `FORMAT` 区域设置的 `DecimalStyle` 实例。

## 语法

```java
public static DecimalStyle ofDefaultLocale()
```

## 参数

此方法不接受任何参数。

## 返回值

该方法为默认的 `FORMAT` 区域设置返回一个 `DecimalStyle` 实例。

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

        System.out.println("DecimalStyle for "
                           + "default FORMAT locale: "
                           + ds.ofDefaultLocale());
    }
}
```

## 输出

```java
DecimalStyle for default FORMAT locale: DecimalStyle[0+-.]
```

## 参考

`https://docs.oracle.com/javase/10/docs/api/java/time/format/DecimalStyle.html#ofDefaultLocale()`