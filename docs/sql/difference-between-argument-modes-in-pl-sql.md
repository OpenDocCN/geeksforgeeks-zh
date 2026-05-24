# PL/SQL 中参数模式的区别

> 原文:[https://www . geesforgeks . org/parameter-modes-in-pl-SQL/](https://www.geeksforgeeks.org/difference-between-argument-modes-in-pl-sql/)

**[论证模式](https://www.geeksforgeeks.org/argument-modes-in-pl-sql/)** 基本上是用来描述形式参数的行为。子程序中使用的参数模式有三种:输入模式、输出模式和输入输出模式。

这些解释如下:

1.  **IN 模式:**
    是子程序中默认的参数模式。该模式将常量值从调用环境传递到子程序中。
2.  **输出模式:**
    该模式将子程序中的一个值传递给调用环境。

*   **IN OUT Mode :**
    This mode is a mixture of both IN and OUT mode. Just like IN mode, it passes a value from the calling environment in subprogram and like a OUT mode, it possibly pass different value from the subprogram back to the calling environment using the same parameter.

    **输入、输出和输入输出模式的区别:**

    <center>

    | 正流行 | 输出模式 | 输入输出模式 |
    | --- | --- | --- |
    | 这是默认模式。 | 必须指定它。 | 必须指定它。 |
    | 在子程序中传递这个值。 | 该值返回到调用环境。 | 在这种情况下，值被传递到子程序中，并返回到调用环境。 |
    | 在这个形式参数中充当常数。 | 在这个形式参数中充当未初始化的变量。 | 在这个形式参数中充当初始化变量。 |
    | 在这个实际的参数可以是文字，印象，常数或初始化变量。 | 在这个实际参数中必须是一个变量。 | 在这个实际参数中必须是一个变量。 |
    | 可以将其指定为默认值。 | 不能将其指定为默认值。 | 也不能将其指定为默认值。 |
    | 它执行只读操作。 | 它只执行写操作。 | 它执行读和写操作。 |

    </center>