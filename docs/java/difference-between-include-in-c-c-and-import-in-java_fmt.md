# C/C++中的`#include`和Java中的`import`的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-include-in-c-c-and-import-in-java/](https://www.geeksforgeeks.org/difference-between-include-in-c-c-and-import-in-java/)

## `#include` in C/C++

在[C语言](https://www.geeksforgeeks.org/c-language-set-1-introduction/)的情况下，`#include`是程序中的标准或用户自定义文件，它告诉预处理器将另一个文件的内部内容插入到程序的源代码中。

**语法：**

```c
#include <stdio.h>
```

**程序 1：**
下面是一个C程序来演示`#include`的使用：

```c
// C Program to demonstrate use of #include
#include <stdio.h>

// Header file loads all the
// necessary Input output
// file at beginning only

// Driver Code
int main()
{
    printf("GeeksforGeeks");
    return 0;
}
```

**输出：**

```
GeeksforGeeks
```

## `import` in Java

在[Java](https://www.geeksforgeeks.org/java/)中，`import`语句用于加载整个包或包中的某些类。它写在类定义之前和包语句之后（如果有的话）。

**语法：**

```java
import java.util.*;
```

**程序 2：**
下面是一个Java程序来演示使用`import`语句：

```java
// Java program to demonstrate use of import
import java.io.*;

// import statement doesn't load
// all the necessary files at
// beginning rather it loads
// only those files which it
// needs at the runtime
class GFG {
    public static void main(String[] args)
    {
        System.out.println("GeeksforGeeks");
    }
}
```

**输出：**

```
GeeksforGeeks
```

## 区别

C/C++中的`#include`和Java中的`import`都是用来加载预定义的头文件或包的，但有一定的区别，如下所列：

| 序列号 | `#include` in C/C++ | `import` in Java |
| :--- | :--- | :--- |
| **1** | 必须使用`#include`语句来包含标准头文件。 | `import`语句是可选的。 |
| **2** | 它只在开始时加载文件。 | 开始时不会加载任何类文件。每当使用一个特定的类时，将只加载相应的类文件。 |
| **3** | 不必要的内存和处理器时间浪费。 | 没有这样浪费内存和处理器的时间。 |
| **4** | 程序的大小增加。 | 不增加程序的大小。 |
| **5** | 它也被称为静态包含。 | 它也被称为动态包含。 |