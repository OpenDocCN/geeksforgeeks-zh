# C 库函数

> 原文：[https://www.geeksforgeeks.org/c-library-functions/](https://www.geeksforgeeks.org/c-library-functions/)

[C](https://www.geeksforgeeks.org/c-language-set-1-introduction/) 中的标准函数库是一个巨大的子库，每个子库包含几个[函数](https://www.geeksforgeeks.org/functions-in-c/)的代码。为了利用这些库，通过使用[头文件](https://www.geeksforgeeks.org/header-files-in-c-cpp-and-its-uses/)链接更广泛的库中的每个库。这些函数的定义出现在它们各自的头文件中。为了使用这些[功能](https://www.geeksforgeeks.org/functions-in-c/)，我们必须在程序中包含头文件。下面是一些带有描述的头文件：

| 编号 | 头文件 | 描述 |
| :--- | :--- | :--- |
| 1 | `<assert.h>` | 它检查我们期望在正常情况下为真的表达式的值。如果表达式是非零值，`assert`宏不执行任何操作。 |
| 2 | `<complex.h>` | 一组用于操作复数的函数。 |
| 3 | `<float.h>` | 定义宏常量并指定浮点库的实现特定属性。 |
| 4 | `<limits.h>` | 这些限制规定变量不能存储超出这些限制的任何值，例如，一个`unsigned char`最多可以存储255个值。 |
| 5 | `<math.h>` | `math.h`头文件定义了各种数学函数和一个宏。此库中的所有函数都接受`double`作为参数并返回`double`作为结果。 |
| 6 | `<stdio.h>` | `stdio.h`头文件定义了三种变量类型、几个宏以及用于输入和输出的各种函数。 |
| 7 | `<time.h>` | 定义日期和时间处理函数。 |
| 8 | `<string.h>` | 字符串被定义为字符数组。字符数组和字符串之间的区别在于字符串以特殊字符`'\0'`结尾。 |

## 实现

我们用一个 [C 程序](https://www.geeksforgeeks.org/c/)来讨论一下基础库的实现：

### `stdio.h`

这个库是用来使用 [`printf()`函数](https://www.geeksforgeeks.org/return-values-of-printf-and-scanf-in-c-cpp/)的，头文件`<stdio.h>`应该包含在程序中。下面是实现上述方法的 C 程序：

```cpp
// C program to implement
// the above approach
#include <stdio.h>

// Driver code
int main()
{
    printf("GEEKS FOR GEEKS");
    return 0;
}
```

**Output**

```
GEEKS FOR GEEKS
```