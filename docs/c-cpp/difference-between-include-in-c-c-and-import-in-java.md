# C/c++ 中的#include 和 JAVA 中的 import 的区别

> 原文:[https://www . geesforgeks . org/include-in-c-c 和 import-in-java 之间的区别/](https://www.geeksforgeeks.org/difference-between-include-in-c-c-and-import-in-java/)

[**# include In C/c++**](https://www.geeksforgeeks.org/c-c-include-directive-with-examples/)**:**在 [C 语言](https://www.geeksforgeeks.org/c-language-set-1-introduction/)的情况下， **#include** 是程序中的标准或用户自定义文件，它告诉预处理器将另一个文件的内部内容插入到程序的源代码中。

**语法:**

> #包括<stdio.h></stdio.h>

**程序 1:**
下面是一个 C 程序来演示**的使用#包括**:

## C

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

```cpp
GeeksforGeeks

```

[**在 Java 中导入**](https://www.geeksforgeeks.org/packages-in-java/) **:** 在 [JAVA](https://www.geeksforgeeks.org/java/) 中， **import** 语句用于加载整个包或包中的某些类。它写在类定义之前和包语句之后(如果有的话)。

**语法:**

> 导入 Java . util . *；

**程序 2:**
下面是一个 Java 程序来演示使用**导入**语句:

## Java 语言(一种计算机语言，尤用于创建网站)

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

```cpp
GeeksforGeeks

```

两者**#都包含在 C/C++** 中**导入在 Java 中**用于加载预定义的头文件或包，但有一定的区别，如下所列:

<figure class="table">T63】没有增加程序的大小。

| **S 号** | **# are all included in C/C/c++ 【T1]** | **Import in Java** |
| **1** | **The import** statement in Java is optional. |
| **2** | It only loads files at the beginning. | No class files will be loaded at first.
Whenever a specific class is used, only the corresponding class file will be loaded. |
| **3** | Unnecessary waste of memory and processor time. | This does not waste memory and processor time. |
| **4** | Program size increases. |
| **5** | It is also called static inclusion. | Also known as dynamic inclusion. |

</figure>