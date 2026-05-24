# Java 中的 `Float.floatToIntBits()` 方法，带示例

> 原文：[https://www.geeksforgeeks.org/float-floattointbits-method-in-java-with-examples/](https://www.geeksforgeeks.org/float-floattointbits-method-in-java-with-examples/)

`Float.floatToIntBits()` 方法是 Java 中的内置函数，根据 *IEEE 754* 浮点“单精度格式”位布局返回指定浮点值的表示。

## 语法

```java
public static int floatToIntBits(float val)
```

## 参数

该方法只接受一个参数 `val`，该参数指定要转换为整数位的浮点数。

## 返回值

该函数返回代表浮点数的 `int` 值。以下是一些特例：

*   如果参数为正无穷大，则结果为 `0x7f800000`。
*   如果参数为负无穷大，则结果为 `0xff800000`。
*   如果参数为 `NaN`，则结果为 `0x7fc00000`。

## 示例

下面的程序说明了 `Float.floatToIntBits()` 方法的使用：

### 程序 1

```java
// Java program to demonstrate
// Float.floatToIntBits() method
import java.lang.*;

class Gfg1 {

    public static void main(String args[])
    {

        float val = 1.5f;

        // function call
        int answer = Float.floatToIntBits(val);

        // print
        System.out.println(val + " in int bits: "
                           + answer);
    }
}
```

**输出：**

```java
1.5 in int bits: 1069547520
```

### 程序 2

```java
// Java program to demonstrate
// Float.floatToIntBits() method

import java.lang.*;

class Gfg1 {

    public static void main(String args[])
    {

        float val = Float.POSITIVE_INFINITY;
        float val1 = Float.NEGATIVE_INFINITY;
        float val2 = Float.NaN;

        // function call
        int answer = Float.floatToIntBits(val);

        // print
        System.out.println(val + " in int bits: "
                           + answer);

        // function call
        answer = Float.floatToIntBits(val1);

        // print
        System.out.println(val1 + " in int bits: "
                           + answer);

        // function call
        answer = Float.floatToIntBits(val2);

        // print
        System.out.println(val2 + " in int bits: "
                           + answer);
    }
}
```

**输出：**

```java
Infinity in int bits: 2139095040
-Infinity in int bits: -8388608
NaN in int bits: 2139095040
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#floatToIntBits(float)](https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#floatToIntBits(float))