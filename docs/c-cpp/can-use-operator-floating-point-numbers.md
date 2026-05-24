# 浮点数可以用%运算符吗？

> 原文:[https://www . geesforgeks . org/can-use-operator-floating-point-numbers/](https://www.geeksforgeeks.org/can-use-operator-floating-point-numbers/)

预测以下程序的输出:

**c++ 中%可以和浮点数一起使用吗？**

```cpp
#include <iostream>
int main()
{
    float f = 9.9f, m = 3.3f;
    float c = f % m;  // LINE 5
    std::cout << c;
    return 0;
}
```

上述程序编译失败，编译器在第 5 行报告以下错误:
输出:

```cpp
invalid operands of types 'float' and 'float' 
to binary 'operator%' 
```

%运算符不能与 C & C++ 中的浮点数一起使用。

**那么 Java 和 C#呢？**
这个行为在 Java & C#中是不一样的。%运算符可用于这些语言中的浮点数。

考虑以下 **Java** 程序的例子:

```cpp
class Test
{
    public static void main(String args[])
    {
        float f = 9.9f, m = 3.3f;
        float c = f % m;
        System.out.println(c);
    }
}
```

输出:

```cpp
3.2999997
```

同理试试这个 **C#** 程序。它工作正常:

```cpp
using System;
class Test
{
    public static void Main()
    {
        float f = 9.9f, m = 3.3f;
        float c = f % m;
        Console.WriteLine(c);
    }
}
```

输出:

```cpp
3.3
```

本文由**遇见普拉瓦西**供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论