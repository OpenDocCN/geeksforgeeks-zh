# Java 中的 Charset compareTo()方法，带示例

> 原文：[https://www.geeksforgeeks.org/charset-compareto-method-in-java-with-examples/](https://www.geeksforgeeks.org/charset-compareto-method-in-java-with-examples/)

`compareTo()` 方法是 `java.nio.charset` 包中用于比较两个 `Charset` 对象的内置方法。比较基于字符集的规范名称，并忽略大小写。

## 语法

```java
public final int compareTo(Charset second)
```

## 参数

该函数接受一个强制参数 `second`，用于指定要进行比较的字符集。

## 返回值

该函数在比较两个字符集后，返回一个整数值，该值可以是负数、正数或零。

下面是上述功能的实现：

## 程序 1

```java
// Java program to demonstrate
// the above function

import java.nio.charset.Charset;
import java.util.Iterator;
import java.util.Map;

public class GFG {

    public static void main(String[] args)
    {

        // First charset
        Charset first = Charset.forName("UTF16");

        // Second charset
        Charset second = Charset.forName("UTF-8");

        // Compares and print
        System.out.println(first.compareTo(second));
    }
}
```

**输出：**

```java

```

## 程序 2

```java
// Java program to demonstrate
// the above function
import java.nio.charset.Charset;
import java.util.Iterator;
import java.util.Map;

public class GFG {

    public static void main(String[] args)
    {

        // First charset
        Charset first = Charset.forName("ISO-2022-CN");

        // Second charset
        Charset second = Charset.forName("ISO-2022-CN");
        System.out.println(first.compareTo(second));
    }
}
```

**输出：**

```java

```

**参考：** [https://docs.oracle.com/javase/9/docs/api/java/nio/charset/Charset.html#compareTo-java.nio.charset.Charset-](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/Charset.html#compareTo-java.nio.charset.Charset-)