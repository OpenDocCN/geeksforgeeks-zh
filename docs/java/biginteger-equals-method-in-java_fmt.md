# Java 中的 BigInteger equals() 方法

> 原文: [https://www.geeksforgeeks.org/biginteger-equals-method-in-java/](https://www.geeksforgeeks.org/biginteger-equals-method-in-java/)

`java.math.BigInteger.equals(Object x)` 方法将此 `BigInteger` 与作为参数传递的对象进行比较，如果两者的值相等，则返回 `true`，否则返回 `false`。

## 语法

```java
public boolean equals(Object x)
```

## 参数

该方法接受单个强制参数 `x`，该参数是要与大整数对象进行比较的对象。

## 返回

当且仅当作为参数传递的对象是一个大整数，其值等于应用该方法的大整数对象时，该方法返回布尔值 `true`。否则将返回 `false`。

## 示例

```java
Input: BigInteger1=2345, BigInteger2=7456
Output: false
Explanation: BigInteger1.equals(BigInteger2)=false.

Input: BigInteger1=7356, BigInteger2=7456
Output: true
Explanation: BigInteger1.equals(BigInteger2)=true.
```

下面的程序说明了 `BigInteger` 类的 `equals()` 方法。

### 示例 1：两者值相等时

```java
// Java program to demonstrate equals() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("321456");
        b2 = new BigInteger("321456");

        // apply equals() method
        boolean response = b1.equals(b2);

        // print result
        if (response) {

            System.out.println("BigInteger1 " + b1
                               + " and BigInteger2 "
                               + b2 + " are equal");
        }
        else {

            System.out.println("BigInteger1 " + b1
                               + " and BigInteger2 "
                               + b2 + " are not equal");
        }
    }
}
```

**输出：**

```java
BigInteger1 321456 and BigInteger2 321456 are equal
```

### 示例 2：两者值不相等时

```java
// Java program to demonstrate equals() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("321456");
        b2 = new BigInteger("456782");

        // apply equals() method
        boolean response = b1.equals(b2);

        // print result
        if (response) {

            System.out.println("BigInteger1 " + b1
                               + " and BigInteger2 "
                               + b2 + " are equal");
        }
        else {

            System.out.println("BigInteger1 " + b1
                               + " and BigInteger2 " + b2 + " are not equal");
        }
    }
}
```

**输出：**

```java
BigInteger1 321456 and BigInteger2 456782 are not equal
```

### 示例 3：当作为参数传递的对象不是 BigInteger 时

```java
// Java program to demonstrate equals() method of BigInteger

import java.math.BigInteger;

public class Main6 {

    public static void main(String[] args)
    {

        // Creating BigInteger object
        BigInteger b1;

        b1 = new BigInteger("321456");
        String object = "321456";

        // apply equals() method
        boolean response = b1.equals(object);

        // print result
        if (response) {

            System.out.println("BigInteger1 " + b1
                               + " and String Object "
                               + object + " are equal");
        }
        else {

            System.out.println("BigInteger1 " + b1
                               + " and String Object "
                               + object + " are not equal");
        }
    }
}
```

**输出：**

```java
BigInteger1 321456 and String Object 321456 are not equal
```

## 参考

[https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#equals(java.lang.Object)](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#equals(java.lang.Object))