# Java 中的 ChronoField checkValidIntValue() 方法示例

> 原文：[https://www.geeksforgeeks.org/chronofield-checkvalidintvalue-method-in-java-with-examples/](https://www.geeksforgeeks.org/chronofield-checkvalidintvalue-method-in-java-with-examples/)

`ChronoField` 枚举的 `checkValidIntValue()` 方法用于检查作为参数传递的值对于该时域常量是否有效，即值是否符合整数范围。

## 语法

```java
public int checkValidIntValue(long value)
```

## 参数

该方法接受一个参数 `value`，表示要检查的值。

## 返回值

这个方法返回传入的值。

## 示例程序

下面的程序说明了 `ChronoField.checkValidIntValue()` 方法：

### 程序 1

```java
// Java program to demonstrate
// ChronoField.checkValidIntValue() method

import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // get chronoField
        ChronoField chronoField
            = ChronoField.valueOf("HOUR_OF_DAY");

        // apply checkValidIntValue()
        int validInt
            = chronoField.checkValidIntValue(21);

        // print
        System.out.println("Value passed :"
                           + validInt);
    }
}
```

**输出：**

```java
Value passed :21
```

### 程序 2

```java
// Java program to demonstrate
// ChronoField.checkValidIntValue() method

import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // get chronoField
        ChronoField chronoField
            = ChronoField.valueOf("YEAR_OF_ERA");

        // apply checkValidIntValue()
        int validInt
            = chronoField.checkValidIntValue(2021);

        // print
        System.out.println("Value passed :"
                           + validInt);
    }
}
```

**输出：**

```java
Value passed :2021
```

参考文献：[https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoField.html#checkValidIntValue(long)](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoField.html#checkValidIntValue(long))