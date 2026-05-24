# Java 中的 `Long.signum()` 方法

> 原文：[`https://www.geeksforgeeks.org/long-signum-method-in-java/`](https://www.geeksforgeeks.org/long-signum-method-in-java/)

符号函数也称为符号函数，是一种提取实数符号的奇数数学函数。
`java.lang.Long.signum()` 方法用于获取指定 `long` 值的 `signum` 函数。对于正值、负值和零，该方法分别返回 `1`、`-1` 和 `0`。

## 语法

```java
public static int signum(long num)
```

## 参数

该方法接受一个 `long` 型参数 `num`，在其上执行符号操作。

## 返回值

该方法返回指定 `long` 值的 `signum` 函数。如果指定值为：

*   负，则该方法返回 `-1`。
*   零，则该方法返回 `0`。
*   正，则该方法返回 `1`。

## 示例

```java
Input: (Long) 2731766
Output: 1

Input: (Long) -233611 
Output: -1

Input: (Long) 0
Output: 0
```

下面的程序说明了 `java.lang.Long.signum()` 方法：

### 程序 1

```java
// Java program to illustrate the
// Java.lang.Long.signum() Method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        // It will return 1 as long value is greater than 1
        System.out.println(Long.signum(36565531));

        // It will return -1 as long value is less than 1
        System.out.println(Long.signum(-628127));

        // Returns 0 as long value is equal to 0
        System.out.println(Long.signum(0));
    }
}
```

**输出：**

```java
1
-1
0
```

### 程序 2：为十进制值和字符串

```java
// Java program to illustrate the
// Java.lang.Long.signum() Method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        // It will return compile time error
        System.out.println(Long.signum(36565.531));

        // It will return compile time error
        System.out.println(Long.signum("628127"));
    }
}
```

**输出：**

```java
prog.java:10: error: incompatible types: possible lossy conversion from double to long
    System.out.println(Long.signum(36565.531));
                                   ^
prog.java:13: error: incompatible types: String cannot be converted to long
    System.out.println(Long.signum("628127"));
                                   ^
Note: Some messages have been simplified; recompile with -Xdiags:verbose to get full output
2 errors
```