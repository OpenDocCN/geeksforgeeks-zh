# 编写一个在 C 和 C++ 中产生不同结果的程序

> 原文:[https://www . geesforgeks . org/write-c-program-product-differential-result-c/](https://www.geeksforgeeks.org/write-c-program-produce-different-result-c/)

编写一个程序，它可以在 C 和 C++ 中编译和运行，但是当由 C 和 C++ 编译器编译时会产生不同的结果。

这样的节目可以有很多，以下是其中的一些。

**1)** 字符文字在 C 和 C++ 中有不同的处理方式。在像“a”、“b”这样的 C 字符文字中，..etc 被视为整数，而在 C++ 中被视为字符。(详见[本](https://www.geeksforgeeks.org/g-fact-19/)

例如，下面的程序在 C 中生成 sizeof(int)作为输出，但在 C++ 中生成 sizeof(char)。

```cpp
#include<stdio.h>
int main()
{
  printf("%d", sizeof('a'));
  return 0;
}
```

**2)** 在 C 语言中，每当我们声明一个结构变量时，都需要使用 struct tag。在 C++ 中，结构标记不是必需的。例如，让*学生*有一个结构。在 C 语言中，我们必须使用“*结构学生*来表示学生*变量。在 C++ 中，我们可以省略 struct，只使用“ *Student* ”。
下面是一个基于事实的程序，用 C 和 C++ 产生不同的输出。它在 C 中打印 sizeof(int)，在 C++ 中打印 sizeof(struct T)。*

```cpp
#include <stdio.h>
int T;

int main()
{
    struct T { double x; };  // In C++, this T hides the global variable T, 
                            // but not in C
    printf("%d", sizeof(T));
    return 0;
}
```

**3)** 布尔结果的类型在 C 和 C++ 中是不同的。感谢 Gaurav Jain 提出这一点。

```cpp

// output = 4 in C (which is size of int)
printf("%d", sizeof(1==1)); 

// output = 1 in c++ (which is the size of boolean datatype)
cout << sizeof(1==1); 
```

本文由**阿沛·拉提**供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论