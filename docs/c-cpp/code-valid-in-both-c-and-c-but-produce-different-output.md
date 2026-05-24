# 代码在 C 和 C++ 中都有效，但产生不同的输出

> 原文:[https://www . geesforgeks . org/code-valid-in-both-c-and-c-but-product-different-output/](https://www.geeksforgeeks.org/code-valid-in-both-c-and-c-but-produce-different-output/)

有些语法结构对 C 和 C++ 都有效，但在两种语言中编译和运行时会有不同的行为。

还可以利用一些差异来创建用两种语言编译但行为不同的代码。例如，以下函数在 C 和 C++ 中将返回不同的值:

**示例代码在 C 和 C++ 中都有效，但编译时给出不同的答案:**

```cpp
// C code that is valid in both
// C and C++ but produce different
// behavior when compiled.

#include <stdio.h>

// extern keyword for variable
// declaration without define
extern int S;

// function for struct
int differCAndCpp(void)
{
    // create a structure
    struct S {
        int a;
        int b;
    };

    // return sizeof integer variable
    return sizeof(S);
}
// Main driver
int main()
{
    // call function differCAndCpp()
    printf("%d", differCAndCpp());
    return 0;
}
```

**输出:**

```cpp
4
```

**c++ 中的代码**

```cpp
// C++ code that is valid in both
// C and C++ but produce different
// behavior when compiled.

#include <iostream>
using namespace std;

// extern keyword used for variable
// declaration without define
extern int S;

// function for struct
int differCAndCpp(void)
{
    // create a structure
    struct S {
        int a;
        int b;
    };

    // return sizeof structure
    // in c++
    return sizeof(S);
}

// Main driver
int main()
{
    // call function differCAndCpp()
    printf("%d", differCAndCpp());
    return 0;
}
```

**输出:**

```cpp
8
```

我们可以看到两个代码相同，但输出不同。这是因为 C 在结构标签前需要 struct(所以 sizeof(S)指的是变量)，但是 C++ 允许省略它(所以 sizeof(S)指的是隐式 typedef)。

请注意，当 [extern](https://www.geeksforgeeks.org/understanding-extern-keyword-in-c/) 声明放在函数内部时，结果是不同的:那么函数范围内存在同名的标识符会禁止隐式 [typedef](https://www.geeksforgeeks.org/typedef-versus-define-c/) 对 C++ 生效，C 和 C++ 的结果也是一样的。还要注意的是，上例中的歧义是由于在[大小的](https://www.geeksforgeeks.org/sizeof-operator-c/)运算符中使用了括号。

**使用 sizeof T 会期望 T 是一个表达式而不是一个类型，因此该示例不会给出与 C++ 相同的结果。**

**相关文章:**

*   [The difference between Struct in C and C++ ](https://www.geeksforgeeks.org/difference-c-structures-c-structures/)
*   [Write a program to produce different results in C and C++ ](https://www.geeksforgeeks.org/write-c-program-produce-different-result-c/)

参考:-https://en . Wikipedia . org/wiki/Compatibility _ of _ C _ 和 _C%2B%2B