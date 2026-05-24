# Java中的Locale.Category.values()方法及示例

> 原文：[https://www.geeksforgeeks.org/locale-category-values-method-in-java-with-examples/](https://www.geeksforgeeks.org/locale-category-values-method-in-java-with-examples/)

`java.util.Locale.Category`枚举的`values()`方法用于获取`Locale.Category`枚举类型的常量值，按照它们的声明顺序。这个方法返回一个常量数组，因此也可以迭代。

## 语法
```java
public static Locale.Category[] values()
```

## 参数
此方法不接受任何参数。

## 返回类型
这个方法返回一个`Locale.Category`枚举类型的常量**数组**。

## 异常
这个方法不抛出任何异常。

## 程序1
```java
// Java program to demonstrate
// the above method

import java.util.*;
import java.util.Locale.*;

public class LocaleCategoryDemo {
    public static void main(String[] args)
    {

        // Getting the array of constants
        // of Locale.Category
        System.out.println("Array of constants: "
                           + Arrays.toString(
                                 Locale.Category
                                     .values()));
    }
}
```

## 输出
```java
Array of constants: [DISPLAY, FORMAT]
```

## 参考
[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Category.html#values--](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Category.html#values--)