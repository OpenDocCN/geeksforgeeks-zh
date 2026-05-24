# 如何处理 Java 中的 `UnsatisfiedLinkError`？

> 原文：[https://www.geeksforgeeks.org/how-to-handle-java-lang-unsatisfiedlinkerror-in-java/](https://www.geeksforgeeks.org/how-to-handle-java-lang-unsatisfiedlinkerror-in-java/)

## 错误定义

`Java.lang.UnsatisfiedLinkError` 是 `LinkageError` 类的子类。当 Java 虚拟机（JVM）没有找到声明为 `native` 的方法时，它将抛出此错误。

## 发生时机与原因

`Java.lang.UnsatisfiedLinkError` 通常发生在程序运行期间（注：原文“编译期间”有误，应为加载或运行时）。这是因为 JVM 无法找到原生库（native library），即一个只包含特定操作系统原生代码的库，例如 Windows 中的 `.dll` 文件、Linux 中的 `.so` 文件或 Mac 中的 `.dylib` 文件。

## 错误层次结构

该错误的层次结构如下所示：

```
Java.lang.Object
    Java.lang.Throwable
        Java.lang.Error
            Java.lang.LinkageError
                Java.lang.UnsatisfiedLinkError
```

## 代码示例

```java
// Java Program to Illustrate UnsatisfiedLinkError

// Importing input output classes
import java.io.*;

// Main class
public class GFG {

    // Loading the External Library
    // "libfile" is name of C file
    static {
        System.loadLibrary("libfile");
    }

    // Method 1
    // To define externally in C file
    native void cfun();

    // Method 2
    // Main driver method
    public static void main(String[] args) {
        // Creating the object of above class inside main()
        GFG g = new GFG();

        // Calling over the above method
        g.cfun();
    }
}
```