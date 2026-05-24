# Java 中的十进制格式符号 hashCode()方法，示例

> 原文: [https://www.geeksforgeeks.org/decimalformatsymbols-hashcode-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-hashcode-method-in-java-with-examples/)

[`DecimalFormatSymbols`](https://www.geeksforgeeks.org/tag/java-text-package/) 类的 [`hashCode()`](https://www.geeksforgeeks.org/tag/java-text-package/) 方法用于获取这个十进制格式符号的 [`hashCode`](https://www.geeksforgeeks.org/tag/java-text-package/) 值。这个方法返回一个代表 [`hashCode`](https://www.geeksforgeeks.org/tag/java-text-package/) 值的整数。

## 语法

```java
public int hashCode()
```

## 参数

此方法不接受任何参数。

## 返回值

这个方法返回一个 `int`，它是这个十进制格式符号的哈希值。

## 异常

这个方法不抛出任何异常。

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

        System.out.println("DecimalFormatSymbols: "
                           + dfs);

        System.out.println("HashCode value: "
                           + dfs.hashCode());
    }
}
```

## 输出

```java
DecimalFormatSymbols: java.text.DecimalFormatSymbols@1073a
HashCode value: 67386
```

## 参考

[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#hashCode--](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#hashCode--)