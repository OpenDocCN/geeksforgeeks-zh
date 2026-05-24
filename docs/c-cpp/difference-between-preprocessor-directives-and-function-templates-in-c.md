# c++ 中预处理器指令和函数模板的区别

> 原文:[https://www . geesforgeks . org/预处理器指令和函数模板之间的区别-in-c/](https://www.geeksforgeeks.org/difference-between-preprocessor-directives-and-function-templates-in-c/)

[预处理器指令](https://www.geeksforgeeks.org/cc-preprocessors/)是在编译之前处理我们的源代码的程序。在 C / C++ 中，编写程序和执行程序之间涉及许多步骤。

下面是说明函数模板功能的程序:

## C++

```cpp
// C++ program to illustrate
// preprocessor directives
#include <bits/stdc++.h>

#define min(a, b) ((a < b) ? a : b)

using namespace std;

// Driver code
int main()
{
    int a = 2, b = 4;

    // Find the minimum of a and b
    cout << "Minimum of both is: "
         << min(a, b);

    return 0;
}
```

**Output:**

```cpp
Minimum of both is: 2

```

[函数模板](https://www.geeksforgeeks.org/templates-cpp/)是[通用函数](https://www.geeksforgeeks.org/generics-in-c/)，可以处理不同的数据类型，而不需要任何单独的代码。

下面是说明函数模板功能的程序:

## C++

```cpp
// C++ program to illustrate the use
// of Function Templates
#include <iostream>
#include <stdio.h>
using namespace std;

// Function Template
template <class T>
T Min(T x, T y)
{
    return (x < y) ? x : y;
}

// Driver Code
int main()
{
    int a = 4, b = 8;

    // Find the minimum of a and b
    cout << "Minimum of both is: " << min(a, b);

    return 0;
}
```

**Output:**

```cpp
Minimum of both is: 4

```

函数模板用于制作[通用函数](https://www.geeksforgeeks.org/generics-in-c/)，该函数可以使用任何[数据类型](https://www.geeksforgeeks.org/c-data-types/)。例如，用于计算任何类型的 2 个最小值的函数模板可以定义为:

```cpp
template <class T>
T minimum(T a, T b)
{
   return (a < b) ? a : b;
}
```

但是，该任务也可以使用使用预处理器指令[**#定义**](https://www.geeksforgeeks.org/interesting-facts-preprocessors-c/) 创建的 [**预处理器指令**](https://www.geeksforgeeks.org/cc-preprocessors/) 来执行。所以，这两个数字的最小值可以定义为:

```cpp
#define minimum(a, b) ((a < b) ? a : b)
```

预处理器指令也可以通过使用以下语句来实现:

```cpp
minimum(30, 35);
minimum(30.5, 40.5);
```

在 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中，我们大多数人更喜欢使用模板而不是预处理器指令，因为:

*   在预处理器指令的情况下，没有类型检查。但是在模板的情况下，完全类型检查是由编译器完成的。
*   预处理器指令会调用意外的结果。考虑一个[宏](https://www.geeksforgeeks.org/c-language-2-gq/macro-preprocessor-gq/)，它计算任意数字的平方为:

```cpp
#define sqr(x) (x*x)
```

*   现在如果使用下面的语句调用这个宏，x = sqr(4+4)；那么预期输出是 64，但是它生成 24，因为宏体中的任何 x 都被 4 + 4 替换，这导致 x = 4 + 4 * 4 + 4 = 24，但是在模板的情况下，没有获得这样的意外结果。

下面是两者的表格区别:

<figure class="table">数据类型 t88

| **S 号** | **preprocessor instruction** | **Function template** |
| **1** | There is no full-type check | There are full-type checks. |
| Two | They are used together with **# to define** preprocessor instructions. |
| **4** | They will lead to an unexpected result. | Without such unexpected results. |
| **5** | They do not guarantee the type safety in the example. | They do guarantee the type safety. |
| **6** | They don't have clear and complete specialization. | They don't have clear and complete specialization. |

</figure>