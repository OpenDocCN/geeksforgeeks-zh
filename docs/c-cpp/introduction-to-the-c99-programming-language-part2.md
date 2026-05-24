# C99 编程语言介绍:第二部分

> 原文:[https://www . geesforgeks . org/c99 编程语言简介-part2/](https://www.geeksforgeeks.org/introduction-to-the-c99-programming-language-part2/)

在本文中，我们将会发现 C89 的一些更有趣的补充，它给了我们 C99 标准:

1.  [**【变量参数列表】**](https://www.geeksforgeeks.org/variable-length-argument-c/) **:** C99 对[预处理器](https://www.geeksforgeeks.org/cc-preprocessors/)进行了一点小改动。[宏](https://www.geeksforgeeks.org/interesting-facts-preprocessors-c/)可以接受可变数量的参数。这些宏在其声明中由**省略号(…)** 表示。这些变量参数由内置的预处理器标识符**_ _ VA _ RABLES**表示。

## C

```cpp
#include <stdio.h>
#include <string.h>

#define compare(compfunc, ...) compfunc(__VA_ARGS__)

int main()
{
    // Here compare(strlen, "one")
    // transforms to strlen("one")
    printf("Length is %lu\n",
           compare(strlen, "one"));

    // compares variable arguments
    printf("String Comparison Result: %d\n",
           compare(strcmp, "one", "one"));

    return 0;
}
```

**Output:** 

```cpp
Length is 3
String Comparison Result: 0
```

2.  [**_Pragma 运算符**](https://www.geeksforgeeks.org/pragma-directive-in-c-c/) **:** C99 通过使用运算符 _Pragma 指定 **pragma** 实现。
    **语法:**

```cpp
_Pragma("directive")

directive is the pragma being called.
```

1.  This _Pragma operator helps pragmas to participate in macro replacement.
    Some Built in Pragmas are: 

<figure class="table">

| 杂注 | 意义 |
| --- | --- |
| STDC 计划 _ 合同开/关/违约 | 如果 STDC FP_CONTRACT 打开，那么浮点数被视为不可分割的单元，由基于硬件的方法处理。 |
| STDC 芬威 _ 接入开/关/默认 | STDC 告诉编译器浮点环境可能被访问。 |
| STDC CX 有限范围开/关/默认 | STDC·CX 告诉编译器，调用复杂值的某些公式是安全的。 |

</figure>

1.  这三个宏很少使用。这个特性解决了“#pragma”的一个主要问题:作为一个指令，它不能作为宏扩展的结果产生。
    [对一些内置的 C89 宏](https://www.geeksforgeeks.org/predefined-macros-in-c-with-examples/)进行了修改，并添加了新的宏，如 __STDC_HOSTED__、__STDC__VERSION、__STDC_IEC_559__(支持浮点运算)、__STDC_IEC_599_COMPLEX__(支持复数运算)、STDC_ISO_10646__(给出了中的指定日期)。

2.  **循环内部变量声明:**在 C89 标准中，循环变量必须在代码初始化之前声明。但是在 C99 中，我们可以在循环初始化部分声明循环变量。for 循环中声明的变量将位于循环的本地。

## C

```cpp
#include <stdio.h>

int main(void)
{
    // declare variable i at initialization
    int n = 5;
    for (int i = 0; i < n; i++)
        printf("%d ", i);
}
```

**Output:** 

```cpp
0 1 2 3 4
```

1.  这里 I 的范围只在循环内。

2.  [**复合文字**](https://www.geeksforgeeks.org/compound-literals-c/) **:** 复合文字是[数组](https://www.geeksforgeeks.org/arrays-in-c-cpp/)、[结构](https://www.geeksforgeeks.org/structures-c/)或[联合](https://www.geeksforgeeks.org/union-c/)表达式，表示给定类型的对象。
    **例:**

```cpp
int *a = (int[]){11, 12, 13}
```

1.  上面的表达式创建了一个指向名为的整数的指针，该指针指向三元素整数值数组的第一个。
    复合文字通常是通过指定带圆括号的类型名，然后在大括号之间加上初始化列表来创建的，如上所示。
    在文件范围内创建的复合文字存在于整个程序中。如果在块内创建复合文字，当块保留时，复合文字将被销毁，即复合文字在块内是局部的，但在块外是未知的。

## C

```cpp
#include <stdio.h>

int main()
{
    int* a = (int[]){ 11, 12, 13 };
    for (int i = 0; i < 3; i++)
        printf("%d ", a[i]);
}
```

**Output:** 

```cpp
11 12 13
```