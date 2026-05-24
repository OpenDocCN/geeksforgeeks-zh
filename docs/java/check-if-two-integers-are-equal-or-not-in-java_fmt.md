# 在 Java 中检查两个整数是否相等

> 原文：[https://www.geeksforgeeks.org/check-if-two-integers-are-equal-or-not-in-java/](https://www.geeksforgeeks.org/check-if-two-integers-are-equal-or-not-in-java/)

在 Java 中检查两个整数是否相等有多种方法。

1.  算术运算符
2.  比较运算符
3.  字符串功能
4.  异或运算符
5.  补码(`~`)和逐位(`&`)运算符

**例**

```java
Input:    FirstNumber = 15
          SecondNumber= 15
Output: Numbers are same

Input:    FirstNumber = 15
          SecondNumber= 25
Output: Numbers are not same
```

## 方法#1：算术运算符

如果两个数相等，那么它们的减法等于 0。

```java
// Check Two Integers are Equal or Not in Java
// using arithmetic operator
import java.io.*;
class GFG {
    public static void main(String[] args)
    {
        int firstNumber = 15;
        int secondNumber = 15;
        if ((firstNumber - secondNumber) == 0)
            System.out.println("Numbers are equal");
        else
            System.out.println("Numbers are not equal");
    }
}
```

**Output**

```java
Numbers are equal
```

## 方法#2：比较运算符

如果两个数相等，则 `if` 条件中的等号运算符返回 `true`，否则返回 `false`。

```java
// Check Two Integers are Equal or Not in Java
// using Comparison Operators
import java.io.*;
class GFG {
    public static void main(String[] args)
    {
        int firstNumber = 15;
        int secondNumber = 15;
        if (firstNumber == secondNumber)
            System.out.println("Numbers are equal");
        else
            System.out.println("Numbers are not equal");
    }
}
```

**Output**

```java
Numbers are equal
```

## 方法#3：字符串函数

将数字转换为字符串，并在 `String` 类中使用 `compareTo()` 方法。如果两个字符串相同，`compareTo()` 方法返回 0，否则返回 1 或 -1。

```java
// Check Two Integers are Equal or Not in Java
// using String functions
import java.io.*;
class GFG {
    public static void main(String[] args)
    {
        String firstNumber = 15 + "";
        String secondNumber = 15 + "";
        if (firstNumber.compareTo(secondNumber) == 0)
            System.out.println("Numbers are equal");
        else
            System.out.println("Numbers are not equal");
    }
}
```

**Output**

```java
Numbers are equal
```

## 方法#4：异或运算

异或属性表示两个相同数字的异或为零。

```java
// Check Two Integers are Equal or Not in Java
// using XOR Operation
import java.io.*;
class GFG {
    public static void main(String[] args)
    {
        int firstNumber = 15;
        int secondNumber = 15;
        if ((firstNumber^secondNumber)==0)
            System.out.println("Numbers are equal");
        else
            System.out.println("Numbers are not equal");
    }
}
```

**Output**

```java
Numbers are equal
```

## 方法#5：补码(`~`)和逐位(`&`)运算符

```java
// Check Two Integers are Equal or Not in Java
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        int firstNumber = 15;
        int secondNumber = 15;
        if ((firstNumber & ~secondNumber) == 0
            && (~firstNumber & secondNumber) == 0)
            System.out.print("Numbers are equal");
        else
            System.out.print("Numbers are not equal");
    }
}
```

**Output**

```java
Numbers are equal
```