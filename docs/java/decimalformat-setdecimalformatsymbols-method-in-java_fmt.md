# DecimalFormat.setDecimalFormatSymbols()方法详解

> 原文：`https://www.geeksforgeeks.org/decimalformat-setdecimalformatsymbols-method-in-java/`

`setDecimalFormatSymbols()`方法是`java.text.DecimalFormat`类的内置方法，用于为此`DecimalFormat`实例设置新的`DecimalFormatSymbols`。程序员或用户不能更改此十进制格式符号。

## 语法

```java
public void setDecimalFormatSymbols(DecimalFormatSymbols newSymbols)
```

## 参数

该函数接受单个参数`newSymbols`，这是用于为此实例设置新十进制格式符号的`DecimalFormatSymbols`实例。

## 返回值

函数不返回值。

下面是上述功能的实现：

### 程序 1

```java
// Java program to illustrate the
// setDecimalFormatSymbols() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

// Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

// Get the DecimalFormatSymbols Instance
        DecimalFormatSymbols dfs = deciFormat.getDecimalFormatSymbols();

// Set the DecimalFormatSymbols
        deciFormat.setDecimalFormatSymbols(dfs);

System.out.println(deciFormat.format(12345.6789));
    }
}
```

## 输出

```java
12,345.679
```

### 程序 2

```java
// Java program to illustrate the
// setDecimalFormatSymbols() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

// Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

// Get the DecimalFormatSymbols Instance
        DecimalFormatSymbols dfs = deciFormat.getDecimalFormatSymbols();
        dfs.setZeroDigit('\u0660');

// Set the DecimalFormatSymbols
        deciFormat.setDecimalFormatSymbols(dfs);

System.out.println(deciFormat.format(12345.6789));
    }
}
```

## 输出

```java
١٢,٣٤٥٫٦٧٩
```

## 参考

`https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setDecimalFormatSymbols(java.text.DecimalFormatSymbols)`