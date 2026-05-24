# 十进制格式符号在 Java 中设置符号(字符)方法，示例

> 原文：[https://www.geeksforgeeks.org/decimalformatsymbols-setminussignchar-method-in-java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-setminussignchar-method-in-java-with-examples/)

`DecimalFormatSymbols` 类中的 `setMinusSign()` 方法用于设置此 `DecimalFormatSymbols` 的区域设置的负号字符。此方法将表示减号的字符作为参数。

## 语法

```java
public void setMinusSign(char minusSign)
```

## 参数

该方法接受 `minusSign` 作为参数，该参数是用于表示该十进制格式符号负号的字符。

## 返回值

此方法不返回任何内容。

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

        System.out.println("Current Character used"
                           + " for minus sign: "
                           + dfs.getMinusSign());

        char minusSign = '*';

        dfs.setMinusSign(minusSign);

        System.out.println("Updated Character used"
                           + " for minus sign: "
                           + dfs.getMinusSign());
    }
}
```

## 输出

```java
Current Character used for minus sign: -
Updated Character used for minus sign: *
```

### 参考
[https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getMinusSign--](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#getMinusSign--)