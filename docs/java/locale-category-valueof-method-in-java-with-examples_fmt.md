# Locale.Category.valueOf()方法示例

> 原文：[https://www.geeksforgeeks.org/locale-category-valueof-method-in-java-with-examples/](https://www.geeksforgeeks.org/locale-category-valueof-method-in-java-with-examples/)

`java.util.Locale.Category`枚举的`valueOf()`方法用于获取`Locale.Category`枚举中指定常量的值。此方法将常量名称作为参数。

## 语法
```java
public static Locale.Category valueOf(String name)
```

## 参数
该方法接受一个参数`name`，这是一个常量名称，其值将从`Locale.Category`枚举中检索。

## 返回类型
这个方法返回一个具有指定名称值的`Locale.Category`枚举类型的实例。

## 异常
这个方法不抛出任何异常。

### 程序1
```java
// Java program to demonstrate
// the above method

import java.util.*;
import java.util.Locale.*;

public class LocaleCategoryDemo {
    public static void main(String[] args)
    {

        String name = "DISPLAY";

        // Getting the constant
        // of Locale.Category
        System.out.println("Locale.Category "
                           + "value of "
                           + name + ": "
                           + Locale.Category
                                 .valueOf(name));
    }
}
```

## 输出
```java
Locale.Category value of DISPLAY: DISPLAY
```

### 程序2
```java
// Java program to demonstrate
// the above method

import java.util.*;
import java.util.Locale.*;

public class LocaleCategoryDemo {
    public static void main(String[] args)
    {

        String name = "FORMAT";

        // Getting the constant
        // of Locale.Category
        System.out.println("Locale.Category "
                           + "value of "
                           + name + ": "
                           + Locale.Category
                                 .valueOf(name));
    }
}
```

## 输出
```java
Locale.Category value of FORMAT: FORMAT
```

## 参考
[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Category.html#valueOf-java.lang.String-](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Category.html#valueOf-java.lang.String-)