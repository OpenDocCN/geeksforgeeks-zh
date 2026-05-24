# 生成随机十六进制字节的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-generate-random-hexadecimal-bytes/](https://www.geeksforgeeks.org/java-program-to-generate-random-hexadecimal-bytes/)

要生成随机十六进制字节，首先可以使用 [`Random.nextInt()`](https://www.geeksforgeeks.org/java-util-random-nextint-java/) 生成十进制形式的随机字节，然后使用 [`Integer.toHexString()`](https://www.geeksforgeeks.org/java-lang-integer-tohexstring-method-examples/) 方法将其转换为十六进制形式。

## 1. `java.util.Random.nextInt()`

[`nextInt()`](https://www.geeksforgeeks.org/java-util-random-nextint-java/) 方法用于从这个随机数生成器的序列中获取下一个整数。这里还可以指定范围，该范围将返回一个介于 0（包括 0）和指定数字（不包括 0）之间的数字。

**声明**

```java
public int nextInt()
```

**返回值：** 方法调用从随机数生成器序列中返回下一个整数。

**例：**

```java
// Here printing n is a random integer.
int n = ran.nextInt();
```

## 2. `Integer.toHexString()`

[`toHexString()`](https://www.geeksforgeeks.org/java-lang-integer-tohexstring-method-examples/) 是 Java 中的一个内置方法，它将整数参数的字符串表示形式作为基数为 16 的无符号整数返回。该函数在整数数据类型中采用单个参数作为参数。

**声明**

```java
public static String toHexString(int i)
```

**返回值：** 它将整数参数的字符串表示形式返回为以 16 为基数的无符号整数。

**例：**

```java
Input:13
Output:d

Input:14
Output:e
```

### 例

## Java 程序

```java
// Java Program to Generate Random Hexadecimal Bytes

import java.io.*;
import java.util.Random;

class GFG {
    public static void main(String[] args)
    {
        // Random instance
        Random r = new Random();
        int n = r.nextInt();

        // n stores the random integer in decimal form
        String Hexadecimal = Integer.toHexString(n);

        // toHexString(n) converts n to hexadecimal form
        System.out.println("Random Hexadecimal Byte: "
                           + Hexadecimal);
    }
}
```

**输出**

```
Random Hexadecimal Byte: 61fdc065
```