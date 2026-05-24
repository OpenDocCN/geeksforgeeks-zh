# Java中Locale.FilteringMode.values()方法详解

> 原文：[https://www.geeksforgeeks.org/locale-filteringmode-values-method-in-java-with-examples/](https://www.geeksforgeeks.org/locale-filteringmode-values-method-in-java-with-examples/)

在Java中，`java.util.Locale.FilteringMode`枚举的`values()`方法用于获取该`Locale.FilteringMode`枚举类型的所有常量值，并按照它们的声明顺序返回。此方法返回一个常量数组，因此也可以对其进行迭代。

## 语法

```java
public static Locale.FilteringMode[] values()
```

## 参数
此方法不接受任何参数。

## 返回类型
此方法返回一个`Locale.FilteringMode`枚举类型的常量数组。

## 异常
此方法不抛出任何异常。

## 示例程序

```java
// Java program to demonstrate
// the above method

import java.util.*;
import java.util.Locale.*;

public class LocaleFilteringModeDemo {
    public static void main(String[] args)
    {

        // Getting the array of constants
        // of Locale.FilteringMode
        System.out.println("Array of constants: "
                           + Arrays
                                 .toString(
                                     Locale.FilteringMode
                                         .values()));
    }
}
```

## 输出

> 常量数组: [AUTOSELECT_FILTERING, EXTENDED_FILTERING, IGNORE_EXTENDED_RANGES, MAP_EXTENDED_RANGES, REJECT_EXTENDED_RANGES]

## 参考
[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.FilteringMode.html#values--](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.FilteringMode.html#values--)