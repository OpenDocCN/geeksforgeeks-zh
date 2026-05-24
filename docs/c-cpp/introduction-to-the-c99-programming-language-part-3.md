# C99 编程语言介绍:第三部分

> 原文:[https://www . geeksforgeeks . org/简介-c99-编程语言-part-3/](https://www.geeksforgeeks.org/introduction-to-the-c99-programming-language-part-3/)

在阅读本文之前，请先阅读 C99 编程语言简介(第一部分)和 C99 编程语言简介(第二部分)。

1.  **Addition of library functions:** C99 provides some additional library functions listened below.

    It gives macros like **bool** , **true** and **false** .

    | Library functions | use |
    | --- | --- |
    | Complex. H | Complex. H supports complex operation |
    | Fenfu. H | Fenv. H allows |
    | Inttypes.h. Type | inttypes.h supports processing long numbers (numbers with larger width).
    It defines a standard and portable integer name |
    | ISO 646 hours | Macros defined by ISO 646.h correspond to operators like & & and |
    | stdint.h | stdint.h is included in the **inttypes.h** header file.
    It gives a standard and portable set of integer names. |
    | TGmath.h | TGmath.h defines generic floating-point macors |
    | WChar.h |  |
    | Abbreviation of WCType.h | wctype.h supports multi-byte and wide character classification functions. |

2.  **Addition of [Format Specifiers](https://www.geeksforgeeks.org/format-specifiers-in-c/):** In C99 Standard, **printf()** and **scanf()** functions are modified in such a way that they have ability to handle modifiers **long long** and **unsigned long long**. The format specifier of long long int is ll and unsigned long long int is ul.

    下面的示例程序演示了长整型和无符号长整型值的使用。

    ```cpp
    #include<stdio.h>

    int main()
    {
        long long int a=1121231456;
        unsigned long long int b=1124154632;
        printf("Long Number: %lld and"
    " Unsigned long: %llu",
     a, b);
    }
    ```

3.  **[_ _ func _ _ Identifier](https://www.geeksforgeeks.org/predefined-identifier-__func__-c/):**
    C99 添加 **__func__** 标识符，该标识符返回作为字符串调用的函数的名称。简单来说，如果在 fun1()函数中调用了 _ _ func _ _ 函数，那么它将返回字符串 **fun1** 。
4.  **[隐式 int 声明](https://www.geeksforgeeks.org/implicit-return-type-int-c-language/) :**
    在 C89 标准中，我们不需要在函数中显式声明整数返回类型，即如果我们声明 function_name(参数)，编译器将假定整数为默认返回类型。在 C99 中，不再支持所有隐式函数声明。有些编译器会产生错误，而有些则显示与警告相同的错误。GCC 编译器显示，作为警告。
5.  **Void 返回类型:**
    在 C89 标准中，我们可以省略函数的返回值。如果我们编写 **int fun1()** 并在不指定返回值的情况下执行，编译器将采用默认返回值自动执行。该值可以是 0 或垃圾值。但是在 C99 中，如果我们写 **int fun1()** 而没有返回语句，那么编译器会将它视为错误。
6.  **Extended Integer Types:** C99 standard gave several extensions to integer types.

    | 扩展类型 | 意义 |
    | --- | --- |
    | int16_t | 整数正好有 16 位 |
    | int_least16_t | 整数至少有 16 位。 |
    | int_fast32_t | 至少有 32 位的最快整数类型。 |
    | 最大值 t | 保存最大整数类型 |
    | -伊甸园字幕组=-翻译 | 保存最大无符号整数类型 |

    这些一般很少使用。

这些是一些主要的变化，包括增加、改变和删除 C89 中的功能，以获得 C99 标准。