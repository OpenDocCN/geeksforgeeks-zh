# Java 中的 DecimalFormat.getDecimalFormatSymbols() 方法

> 原文：[https://www.geeksforgeeks.org/decimalformat-getdecimalformatsymbols-method-in-java/](https://www.geeksforgeeks.org/decimalformat-getdecimalformatsymbols-method-in-java/)

该方法是 Java 中的一个内置方法，用于获取这个 `DecimalFormat` 实例的 `DecimalFormatSymbols` 的副本。这些符号是固定的，用户不能更改。

**语法**:
```java
public DecimalFormatSymbols getDecimalFormatSymbols()
```

**参数**：该功能不接受任何参数。
**返回值**：该函数返回这个 `DecimalFormat` 实例的 `DecimalFormatSymbols` 的副本。

下面是上述功能的实现：

## 程序 1

```java
// Java program to illustrate the
// getDecimalFormatSymbols() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Get the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Print the DecimalFormatSymbols
        System.out.println(deciFormat.getDecimalFormatSymbols());
    }
}
```

**Output:**
```java
java.text.DecimalFormatSymbols@1073a
```

## 程序 2

```java
// Java program to illustrate the
// getDecimalFormatSymbols() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Get the Currency Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Sets the currency to Canadian Dollar
        deciFormat.setCurrency(
            Currency.getInstance(
                Locale.CANADA));

        // Print the DecimalFormatSymbols
        System.out.println(deciFormat.getDecimalFormatSymbols());
    }
}
```

**Output:**
```java
java.text.DecimalFormatSymbols@1073a
```

**参考**：[https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#getDecimalFormatSymbols()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#getDecimalFormatSymbols())