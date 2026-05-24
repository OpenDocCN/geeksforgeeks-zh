# C/C++ 中的 #include 和 Java 中的 import 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-include-in-c-c-and-import-in-java/](https://www.geeksforgeeks.org/difference-between-include-in-c-c-and-import-in-java/)

## #include In C/C++

在 C 语言的情况下，`#include` 是程序中的标准或用户自定义文件，它告诉预处理器将另一个文件的内部内容插入到程序的源代码中。

**语法:**

> `#include<stdio.h>`

**程序 1:**
下面是一个 C 程序来演示 `#include` 的使用:

```cpp
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

**Output:**

```
GeeksforGeeks
```

## Import In Java

在 Java 中，`import` 语句用于加载整个包或包中的某些类。它写在类定义之前和包语句之后(如果有的话)。

**语法:**

> `import java.util.*;`

**程序 2:**
下面是一个 Java 程序来演示使用 `import` 语句:

```cpp
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

**Output:**

```
GeeksforGeeks
```

两者 `#include` 在 C/C++ 中和 `import` 在 Java 中都用于加载预定义的头文件或包，但有一定的区别，如下所列:

| S 号 | #include In C/C++ | Import In Java |
| :--- | :--- | :--- |
| **1** | `#include` 是必需的。 | `import` 语句在 Java 中是可选的。 |
| **2** | 它在程序开始时加载所有文件。 | 开始时不会加载任何类文件。每当使用特定类时，只会加载相应的类文件。 |
| **3** | 不必要的内存和处理器时间浪费。 | 这不会浪费内存和处理器时间。 |
| **4** | 程序大小会增加。 | 程序大小不会增加。 |
| **5** | 也称为静态包含。 | 也称为动态包含。 |