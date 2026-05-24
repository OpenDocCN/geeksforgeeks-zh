# 使用示例讲解 Java 中的 `DecimalFormatSymbols.clone()` 方法

> 原文：[https://www.geeksforgeeks.org/decimalformatsymbols-clone-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-clone-method-in-java-with-examples/)

`clone()` 方法是 `DecimalFormatSymbols` 类的一部分。在 Java 中，`DecimalFormatSymbols` 类用于表示十进制格式的符号集。此方法的作用是克隆当前的 `DecimalFormatSymbols` 对象。这意味着它将创建一个新的 `DecimalFormatSymbols` 实例，其所有属性都与当前对象相同，并返回这个新实例。

## 语法

```java
public Object clone()
```

## 参数
此方法不接受任何参数。

## 返回值
此方法返回一个 `Object`，它是当前 `DecimalFormatSymbols` 对象的克隆。

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

        System.out.println("Current DecimalFormatSymbols: "
                           + dfs);

        System.out.println("Cloned DecimalFormatSymbols: "
                           + dfs.clone());
    }
}
```

## 输出

```java
Current DecimalFormatSymbols: java.text.DecimalFormatSymbols@1073a
Cloned DecimalFormatSymbols: java.text.DecimalFormatSymbols@1073a
```

## 参考
[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#clone--](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#clone--)