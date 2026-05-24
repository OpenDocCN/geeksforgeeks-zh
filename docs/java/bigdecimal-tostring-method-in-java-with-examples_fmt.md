# Java 中的 BigDecimal.toString() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/bigdecimal-tostring-method-in-java-with-examples/](https://www.geeksforgeeks.org/bigdecimal-tostring-method-in-java-with-examples/)

`BigDecimal.toString()` 方法用于以 `String` 形式表示当前的 `BigDecimal`。如果需要指数，则使用科学计数法。其转换过程遵循以下步骤：

*   `BigDecimal` 的标准规范字符串形式是通过将未缩放值的绝对值（以十进制数字表示）转换为字符“0”到“9”而创建的，且不带前导零。如果值为 0，则使用单个字符“0”。
*   接下来，计算调整后的指数，该指数比转换后的未缩放值的字符数与取反的比例值的字符数之和少 1。即 `-scale + (ulength - 1)`，其中 `ulength` 是以十进制数字表示的未缩放值的绝对值的长度（其精度）。
*   然后，字符形式的指数被添加到转换后的未缩放值之后（可能会插入小数点）。这包括字母“E”，紧接着是转换成字符形式的调整指数。
*   最后，如果未缩放的值小于零，则整个字符串以减号字符“-”作为前缀。如果未缩放值为零或正，则无符号字符作为前缀。

## 语法

```java
public String toString()
```

## 参数

该方法不接受任何参数。

## 返回值

此方法返回这个 `BigDecimal` 数的字符串表示形式。

## 覆盖

此方法覆盖 `Object` 类的 `toString()` 方法。

下面的程序说明了 `toString()` 方法在 Java 中的使用。

### 示例 1：将 BigDecimal 转换为不带科学符号的字符串

```java
// Java program to demonstrate
// toString() method of BigDecimal

import java.math.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating a BigDecimal object
        BigDecimal b;

        // Object of String to hold the number
        String input = "012345678901234567"
                       + "8901234567890123"
                       + "4567890123456789"
                       + "0123456789012345"
                       + "6789012345678901"
                       + "2345678901234567"
                       + "8901234567890123"
                       + "4567890123456789"
                       + "0123456789012345"
                       + "6789012345678901"
                       + "2345678901234567"
                       + "8901234567890123"
                       + "4567890123456789"
                       + "0123456789012345"
                       + "6789012345678901"
                       + "2345678901234567"
                       + "8901234567890123"
                       + "4554324324362432"
                       + "7674637264783264"
                       + "7832678463726478"
                       + "3264736274673864"
                       + "7364732463546354"
                       + "6354632564532645"
                       + "6325463546536453"
                       + "6546325463546534"
                       + "6325465345326456"
                       + "4635463263453264"
                       + "654632498739473";

        // Converting to BigDecimal
        b = new BigDecimal(input);

        // Apply toString() method
        String s = b.toString();

        // Print the result
        System.out.println(s);
    }
}
```

**输出：**

```
1234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234567890123456789012345678901234554324324362432767463726478326478326784637264783264736274673864736473246354635463546325645326456325463546536453654632546354653463254653453264564635463263453264654632498739473
```

### 示例 2：将 BigDecimal 转换为科学符号字符串

```java
// Java program to demonstrate
// toString() method of BigDecimal

import java.math.*;

class GFG {
    public static void main(String[] args)
    {

        // Create a BigDecimal object
        BigDecimal a;

        // Create a String object
        String s;

        // Set precision to 5
        MathContext mc
            = new MathContext(5);

        a = new BigDecimal("4536785E4", mc);

        // apply toString() method
        s = a.toString();

        // print the result
        System.out.println(s);
    }
}
```

**输出：**

```
4.5368E+10
```

## 参考

[https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#toString()](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigDecimal.html#toString())