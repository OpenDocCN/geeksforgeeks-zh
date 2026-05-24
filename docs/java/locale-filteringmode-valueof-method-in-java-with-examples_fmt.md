# Java 中 Locale.FilteringMode valueOf() 方法示例

> 原文：[https://www.geeksforgeeks.org/locale-filteringmode-valueof-method-in-java-with-examples/](https://www.geeksforgeeks.org/locale-filteringmode-valueof-method-in-java-with-examples/)

`java.util.Locale.FilteringMode` 枚举的 `valueOf()` 方法用于获取该 `Locale` 的指定常量的值。`FilteringMode` 枚举类型。此方法将常量名称作为参数。

## 语法

```java
public static Locale.FilteringMode valueOf(String name)
```

## 参数

该方法接受一个参数 `name`，这是一个常量名称，其值将从 `Locale.FilteringMode` 枚举中检索。

## 返回类型

这个方法返回一个 `Locale.FilteringMode` 枚举类型的实例，具有指定名称值。

## 异常

这个方法不抛出任何异常。

## 程序 1

```java
// Java program to demonstrate
// the above method

import java.util.*;
import java.util.Locale.*;

public class LocaleFilteringModeDemo {
    public static void main(String[] args)
    {

        String name
            = "AUTOSELECT_FILTERING";

        // Getting the constant
        // of Locale.FilteringMode
        System.out.println("Locale.FilteringMode"
                           + " value of "
                           + name + ": "
                           + Locale.FilteringMode
                                 .valueOf(name));
    }
}
```

## 输出

```java
Locale.FilteringMode value of AUTOSELECT_FILTERING: AUTOSELECT_FILTERING
```

## 程序 2

```java
// Java program to demonstrate
// the above method

import java.util.*;
import java.util.Locale.*;

public class LocaleFilteringModeDemo {
    public static void main(String[] args)
    {

        String name
            = "EXTENDED_FILTERING";

        // Getting the constant
        // of Locale.FilteringMode
        System.out.println("Locale.FilteringMode"
                           + " value of "
                           + name + ": "
                           + Locale.FilteringMode
                                 .valueOf(name));
    }
}
```

## 输出

```java
Locale.FilteringMode value of EXTENDED_FILTERING: EXTENDED_FILTERING
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.FilteringMode.html#valueOf-java.lang.String-](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.FilteringMode.html#valueOf-java.lang.String-)