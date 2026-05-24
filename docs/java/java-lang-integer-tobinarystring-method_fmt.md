# 爪哇郎。Integer.toBinaryString()方法

> 原文:[https://www . geesforgeks . org/Java-lang-integer-tobinarystring-method/](https://www.geeksforgeeks.org/java-lang-integer-tobinarystring-method/)

`Java.lang.Integer.toBinaryString()`方法返回整数参数的字符串表示形式，以 2 为基数，表示为无符号整数。它接受 `int` 数据类型的参数，并返回相应的二进制字符串。

## 语法:

```java
public static String toBinaryString(int num)
```

参数：该函数接受一个强制参数 `num`。
`num` - 此参数指定要转换为二进制字符串的数字。
其类型为 `int`。

## 返回值:
该函数返回由二进制（基数为 2）中的参数表示的无符号整数值的字符串表示形式。

## 例:

```java
Input : 10 
Output : 1010

Input : 9
Output : 1001
```

```java
// Java program to demonstrate
// java.lang.Integer.toBinaryString() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        int l = 10;
        // returns the string representation of the unsigned int value
        // represented by the argument in binary (base 2)
        System.out.println("Binary is " + Integer.toBinaryString(l));

        l = 9;
        System.out.println("Binary is " + Integer.toBinaryString(l));
    }
}
```

输出:

```java
Binary is 1010
Binary is 1001
```