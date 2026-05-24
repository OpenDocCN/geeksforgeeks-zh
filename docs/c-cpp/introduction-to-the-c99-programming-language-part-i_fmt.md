# C99 编程语言介绍:第一部分

> 原文: [https://www.geeksforgeeks.org/introduction-to-the-c99-programming-language-part-i/](https://www.geeksforgeeks.org/introduction-to-the-c99-programming-language-part-i/)

`C99` 是 1999 年通过的 **ISO/IEC 9899:1999** C 标准规范的别称。本文通过与 C89 标准的比较，重点介绍 C99 新增的功能。在 C99 标准的开发阶段，重新检查了 C 语言的每个元素，分析了使用模式，并预测了未来的需求。C 与 C++ 的关系为整个开发过程提供了背景。由此产生的 C99 标准是对原版优势的证明。

## C99 中增加的关键词

### inline
`inline` 关键字适用于函数。如果我们为任何函数编写 `inline datatype function_name (param)`，就意味着我们指定编译器优化对该函数的调用，即函数的代码将被内联展开而不是被调用。

**示例:**
```cpp
// C program to demonstrate inline keyword
#include <stdio.h>

inline int maximum(int a, int b)
{
    return a > b ? a : b;
}

int main()
{
    int x = 5, y = 10;
    printf("Maximum of %d and %d is %d",
           x, y, maximum(x, y));
    return 0;
}
```

**注意:** 一些编译器未定义对 `maximum()` 的引用。这个内嵌特性很少用作关键字。

上述程序相当于以下程序:
```cpp
#include <stdio.h>

int main()
{
    int x = 5, y = 10;
    printf("Maximum of %d and %d is %d",
           x, y, (x > y ? x : y));
    return 0;
}
```

**Output:**
```
Maximum of 5 and 10 is 10
```

内联函数通过维护结构化的、基于函数的方法来帮助我们创建高效的代码。

### restrict
`restrict` 是一个仅适用于指针的类型限定符。由 `restrict` 限定的指针最初是访问其所指向对象的唯一方式。只有当第二个指针基于第一个指针时，才能通过另一个指针访问该对象。

我们使用 `restrict` 限定符来限制对对象的访问。这些主要用作函数参数或在 `malloc()` 中使用。`restrict` 限定符从不改变程序的语义。

### _Bool
`_Bool` 数据类型在 C99 标准中被添加，用于存储 0 和 1 值。`_Bool` 是一种整数类型。

**注意:** C++ 中的 `bool` 关键字和 C 中的 `_Bool` 不同。

`_Bool` 很少使用，取而代之的是 C99 定义了一个新的头文件 `<stdbool.h>`，它定义了三个宏 `bool`、`true` 和 `false`。

### _Complex
C99 通过 `_Complex` 和 `_Imaginary` 关键字增加了对复数运算的支持。这些关键字为数值编程提供了更好的支持。

**在 `<complex.h>` 中定义的类型:**
*   `float _Complex`
*   `double _Complex`
*   `long double _Complex`

### _Imaginary
如上所述，C99 通过 `_Complex` 和 `_Imaginary` 关键字增加了对复数运算的支持。这些关键字为数值编程提供了更好的支持。

**在 `<complex.h>` 中定义的类型:**
*   `float _Imaginary`
*   `double _Imaginary`
*   `long double _Imaginary`

与布尔数据类型中讨论的相同，复数和虚数并不常用。相反，我们使用头文件 `<complex.h>`，它由内置宏 `complex` 和 `imaginary` 组成。

## 添加类型限定符
C99 中添加的另一个重要方面是引入了 `long long int` 和 `unsigned long long int` 类型修饰符。`long long int` 的范围从 –(2^63) 到 +(2^63)。`unsigned long long int` 的最小范围是从 0 到 +(2^64-1)。这种 `long long int` 允许 64 位整数作为内置类型支持。

## 数组的变化
C99 为数组增加了两个重要特性:

### 变长数组
在 C89 标准中，数组大小必须在数组声明时使用整数常量指定，并且数组大小在编译时是固定的。在 C99 标准中，我们可以声明一个数组，该数组的维度由任何整数表达式指定，这些表达式的值在运行时是已知的。这被称为 **变长数组(VLA)**。

### 类型限定符的包含
在 C99 中，我们可以在数组声明时在方括号内使用关键字 `static`。这只在数组在函数参数中声明时应用，即

**示例:**
```cpp
int fun1(char arr[static 80])
{
    // code
}
```

在上面的例子中，`arr` 总是指向一个 80 个元素的数组，也就是说 `arr` 保证指向包含至少 80 个元素的字符数组的起始元素。如果在函数参数中声明了该数组，我们还可以在方括号内使用关键字 `restrict`、`volatile` 和 `const`。关键字 `restrict` 指定指针是访问对象的唯一初始方式。`const` 表示指针始终指向同一个对象。`volatile` 是允许的，但没有意义。

**示例:**
```cpp
#include <stdio.h>
void fun(int a[static 10])
{
    for (int i = 0; i < 10; i++) {
        a[i] += 1;
        printf("%d ", a[i]);
    }
}

int main()
{
    int a[] = { 1, 2, 3, 4,
                4, 4, 4, 4,
                5, 5, 6, 7,
                8, 9, 10 };
    fun(a);
}
```

**Output:**
```
2 3 4 5 5 5 5 5 6 6
```

## 单行注释
单行注释在 C89 标准中不被接受。C99 标准引入了单行注释，仅在需要简短备注时使用。这些注释以 `//` 开头，并持续到行尾。

例如:
```cpp
// First Comment
int a; // another comment
```

## 标识符的声明
根据 C89 标准，所有标识符都应在代码块的开头声明。如果我们中途需要任何其他标识符，我们不能在那个实例或时间声明。我们需要在开头声明它。C99 改变了这个规则，我们可以在代码中需要时随时声明标识符。

简单来说，我们可以这样看:
```cpp
#include <stdio.h>
int main()
{
    int i;
    i = 1;
    int j; // this declaration is invalid in C89 standard, but valid in C99 and C++
    j = 3;
}
```