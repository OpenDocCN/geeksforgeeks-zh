# 如何在 C、C++ 和 Java 中用空 main()打印“GeeksforGeeks”？

> 原文：[https://www.geeksforgeeks.org/print-geeksforgeeks-empty-main-c/](https://www.geeksforgeeks.org/print-geeksforgeeks-empty-main-c/)

写一个程序，用空 `main()` 函数打印 `GeeksforGeeks`。你不能在 `main()` 里写任何东西。

## C 语言

1.  一种方法是给一个函数应用 GCC 的 `constructor` 属性，使其在 `main()` 之前执行（详见[此文](https://www.geeksforgeeks.org/functions-that-are-executed-before-and-after-main-in-c/)）。

```cpp
#include <stdio.h>

/* Apply the constructor attribute to myStartupFun() 
   so that it is executed before main() */
void myStartupFun(void) __attribute__((constructor));

/* implementation of myStartupFun */
void myStartupFun(void)
{
    printf("GeeksforGeeks");
}

int main()
{
}
```

输出：

```cpp
GeeksforGeeks
```

2.  在 Linux 中，只需覆盖默认的 `_start()` 函数定义，使其作为自定义启动代码工作。请参阅[此文](https://www.geeksforgeeks.org/executing-main-in-c-behind-the-scene/)了解更多。

```cpp
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
}

// _start() function
void _start(void)
{
    printf("GeeeksforGeeks");

    // Call main() function
    int var = main();
    exit(var);
}
```

现在通过以下命令编译它：

```bash
gcc -nostartfiles -o file file.c
```

输出：

```cpp
GeeksforGeeks
```

## C++ 语言

1.  思路是创建一个 `class`，在其构造函数中包含一条 `cout` 语句，并创建该类的一个全局对象。当对象被创建时，构造函数被调用，从而打印出 “GeeksforGeeks”。

```cpp
#include <iostream>

class MyClass {
public:
    MyClass()
    {
        std::cout << "GeeksforGeeks";
    }
} m;

int main()
{
}
```

输出：

```cpp
GeeksforGeeks
```

2.  思路是创建一个 `struct` 并使用与上述相同的逻辑。原因是在 C++ 中，`struct` 和 `class` 是完全相同的数据结构，只是 `struct` 默认为 `public` 可见性，而 `class` 默认为 `private` 可见性。

```cpp
#include <iostream>

struct Mystruct {
    Mystruct()
    {
        std::cout << "GeeksforGeeks";
    }
} obj;

int main() {}
```

输出：

```cpp
GeeksforGeeks
```

3.  通过使用全局变量，思路是将 `printf()` 函数初始化给一个全局变量，但这只在 C++ 语言中有效，因为在 C 语言中我们不能这样初始化全局变量或表达式。

```cpp
#include <cstdio>

int var = printf("GeeksforGeeks");

int main()
{
}
```

输出：

```cpp
GeeksforGeeks
```

## Java 语言

其思想是使用静态块进行打印，实际上 Java 中在 `main()` 方法之外声明的任何静态块都是在 `main` 方法之前执行的。

```java
class Myjava {
    static
    {
        System.out.println("GeeksforGeeks");
    }
    public static void main(String args[])
    {
    }
}
```

输出：

```java
GeeksforGeeks
```

本文由**维基**供稿，[舒巴姆·班萨尔](https://www.quora.com/profile/Shubham-Bansal-209)改进。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。