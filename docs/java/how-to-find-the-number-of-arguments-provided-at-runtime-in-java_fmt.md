# 如何在 Java 中找到运行时提供的参数个数？

> 原文：`https://www.geeksforgeeks.org/how-to-find-the-number-of-arguments-provided-at-runtime-in-java/`

## 命令行参数

Java `命令行参数`是在程序运行时传递的参数。也就是说，为了使程序动态化，可能会有我们在运行时传递参数的情况。通常，通过命令行参数，它们被传递，并且有办法找到所提供的参数的数量以及每个参数的值。

每个 Java 程序都是通过[主方法](https://www.geeksforgeeks.org/main-method-compulsory-java/)启动的，这是静态的，意味着`主方法不需要实例化`。我们可以直接调用。因此，调用了一个 java 文件名，第一个开始的方法是`main()`方法，它有一个`String[]`的输入参数（字符串数组数据类型）。

**语法：**

```java
// Java code with main method.
// It has an input argument
// with String[] datatype

import java.io.*;

class GFG {
    public static void main (String[] args) {

    }
}
```