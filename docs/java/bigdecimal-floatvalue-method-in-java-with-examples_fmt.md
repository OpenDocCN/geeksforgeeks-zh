# Java 中的 floatValue() 方法，带示例

> 原文：[https://www.geeksforgeeks.org/bigdecimal-floatvalue-method-in-java-with-examples/](https://www.geeksforgeeks.org/bigdecimal-floatvalue-method-in-java-with-examples/)

## 方法说明

`floatValue()` 将此 `BigDecimal` 转换为 `float`。如果这个 `BigDecimal` 数值太大，无法表示为 `float`，它将被转换为 `Float.NEGATIVE_INFINITY` 或 `Float.POSITIVE_INFINITY`，视情况而定。请注意，即使返回值是有限的，这种转换也会丢失关于 `BigDecimal` 值精度的信息。

## 语法

```java
public float floatValue()
```

## 参数

此方法不接受参数。

## 返回值

该方法返回一个 `float` 值，该值代表该 `BigDecimal` 的浮点值。

## 示例

```java
Input: BigDecimal1 = 1234
Output: 1234.0

Input: BigDecimal1 = 21545135451354545
Output: 2.15451365E16
Explanation: 
BigDecimal1.floatValue() = 2.15451365E16. 
This BigDecimal is too big 
for a magnitude to represent as a float 
then it will be converted to 
Float.NEGATIVE_INFINITY or 
Float.POSITIVE_INFINITY as appropriate.
```

下面的程序说明了 `BigDecimal` 类的 `floatValue()` 方法。

### 例 1

```java
// Java program to demonstrate
// floatValue() method of BigDecimal

import java.math.BigDecimal;

public class GFG {
    public static void main(String[] args)
    {
        // For user input
        // Use Scanner or BufferedReader

        // Object of String created
        // Holds the value
        String input1
            = "545456468445645468464645";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);

        // Using floatValue() method
        float f = a.floatValue();

        // Display the result
        System.out.println(f);
    }
}
```

**输出：**

```java
5.4545646E23
```

### 例 2

```java
// Java program to demonstrate
// floatValue() method of BigDecimal

import java.math.BigDecimal;

public class GFG {
    public static void main(String[] args)
    {
        // For user input
        // Use Scanner or BufferedReader

        // Object of String created
        // Holds the value
        String input1
            = "984522";

        // Convert the string input to BigDecimal
        BigDecimal a
            = new BigDecimal(input1);

        // Using floatValue() method
        float f = a.floatValue();

        // Display the result
        System.out.println(f);
    }
}
```

**输出：**

```java
984522.0
```

## 参考文献

[https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#floatValue()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#floatValue())