# Java 整数比较符号()方法

> 原文: [https://www.geeksforgeeks.org/java-integer-compareunsigned-method/](https://www.geeksforgeeks.org/java-integer-compareunsigned-method/)

`java.lang` 包的 `Integer` 类的 `compareUnsigned()` 方法比较作为参数给定的两个整数值(`x`，`y`)，**将这些值视为无符号的**，如果(`x`==`y`)，则返回值零，如果(`x` < `y`)，则返回值小于零，如果(`x` > `y`)，则返回值大于零。

## 语法

```java
public static int compareUnsigned(int x, int y)
```

**参数：**
`x` : 第一个要比较的 `int`
`y` : 第二个要比较的 `int`

**返回值：**
此方法在 (`x`==`y`) 时返回值零，如果 (`x` < `y`) 则返回小于零的值，如果 (`x` > `y`) 则返回大于零的值，将值(`x`, `y`)视为无符号数。

## 示例

展示 `java.lang.Integer.compareUnsigned()` 方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Integer.compareUnsigned() method
import java.lang.Integer;

class Gfg {

// driver code
    public static void main(String args[])
    {
        int a = 100;
        int b = 200;

// as 100 less than 200, Output will be a value less than zero
        System.out.println(Integer.compareUnsigned(a, b));

int x = 28;
        int y = 28;

// as 28 equals 28, Output will be zero
        System.out.println(Integer.compareUnsigned(x, y));

int w = 15;
        int z = 8;

// as 15 is greater than 8, Output will be a value greater than zero
        System.out.println(Integer.compareUnsigned(w, z));

int m = 15;
        int n = -8;

// as 15 is greater than -8,
        // but -8 will be treated as an unsigned number
        // which will be greater than 15
        // Output will be a value less than zero
        System.out.println(Integer.compareUnsigned(m, n));
    }
}
```

## 输出

```java

```