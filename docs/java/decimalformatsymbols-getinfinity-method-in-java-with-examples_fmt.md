# Java 中的十进制格式符号 getInfinity()方法，带示例

> 原文: [https://www.geeksforgeeks.org/decimalformatsymbols-getinfinity-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-getinfinity-method-in-java-with-examples/)

`DecimalFormatSymbols` 类中的 `getInfinity()` 方法用于获取表示此十进制格式符号的区域设置中无穷大的字符串。

## 语法

```java
public String getInfinity()
```

## 参数

此方法不接受任何参数。

## 返回值

此方法返回一个表示无限的十进制格式符号的字符串，基于默认的区域设置。

## 异常

此方法不抛出任何异常。

## 程序

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

        System.out.println("Character used"
                           + " for infinity: "
                           + dfs.getInfinity());
    }
}
```

## 输出

```java
Character used for infinity: ∞
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getInfinity--](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getInfinity--)