# C/C++ 预处理器指令|第 2 集

> 原文:[https://www . geesforgeks . org/CPP-预处理器-指令-set-2/](https://www.geeksforgeeks.org/cpp-preprocessor-directives-set-2/)

[C/C++ 预处理器指令基础知识](https://www.geeksforgeeks.org/cc-preprocessors/)

**预处理器指令:**在我们在 C/C++ 中遇到的几乎每一个程序中，我们都会在程序的顶部看到几行，前面有一个 hash (#)符号。这些行由编译器在实际编译开始前进行预处理。这些行的结尾由换行符“\n”标识，没有分号“；”来终止这些线路。
预处理器指令主要用于定义宏、评估条件语句、源文件包含、pragma 指令、行控制、错误检测等。

**在这篇文章中，我们将讨论下面给出的更多类型的预处理器指令:**

1.  条件编译
2.  线路控制
3.  错误指令

现在让我们详细了解一下这些指令:

*   **条件编译**:条件编译指令有助于编译程序的特定部分，或者让我们根据某些条件跳过程序某些特定部分的编译。在我们的[上一篇文章](https://www.geeksforgeeks.org/cc-preprocessors/)中，我们已经讨论了两个这样的指令“ **ifdef** ”和“ **endif** ”。在这篇文章中，我们将讨论 **#ifndef** 、 **#if** 、 **#else** 、 **#elif** 。
    1.  **#ifdef**: This directive is the simplest conditional directive. This block is called a conditional group. The controlled text will get included in the preprocessor output iff the macroname is defined. The controlled text inside a conditional will embrace preprocessing directives. They are executed only if the conditional succeeds. You can nest these in multiple layers, but they must be completely nested. In other words, ‘#endif’ always matches the nearest ‘#ifdef’ (or ‘#ifndef’, or ‘#if’). Also, you can’t begin a conditional group in one file and finish it in another.

        **语法:**

        ```cpp
        #ifdef MACRO
            controlled text
        #endif /* macroname */

        ```

    2.  **#ifndef**: We know that the in #ifdef directive if the macroname is defined, then the block of statements following the #ifdef directive will execute normally but if it is not defined, the compiler will simply skip this block of statements. The #ifndef directive is simply opposite to that of the #ifdef directive. In case of #ifndef , the block of statements between #ifndef and #endif will be executed only if the macro or the identifier with #ifndef is not defined.
        **Syntax :**

        ```cpp
        ifndef macro_name
            statement1;
            statement2;
            statement3;
            .
            .
            .
            statementN;
        endif

        ```

        如果未使用#define 指令定义名为“macroname”的宏，则只执行语句块。

    3.  **#if, #else and #elif**: These directives works together and control compilation of portions of the program using some conditions. If the condition with the #if directive evaluates to a non zero value, then the group of line immediately after the #if directive will be executed otherwise if the condition with the #elif directive evaluates to a non zero value, then the group of line immediately after the #elif directive will be executed else the lines after #else directive will be executed.
        **Syntax:**

        ```cpp
        #if macro_condition
           statements
        #elif macro_condition
           statements
        #else
           statements
        #endif

        ```

        示例:

        ```cpp
        #include<iostream>

        #define gfg 7

        #if gfg > 200
           #undef gfg
           #define gfg 200
        #elif gfg < 50
           #undef gfg
           #define gfg 50
        #else
           #undef gfg
           #define gfg 100
        #endif

        int main()
        {
            std::cout << gfg;  // gfg = 50
        }    
        ```

        输出:

        ```cpp
        50

        ```

        请注意#if、#elif 和#else 链式指令的整个结构是如何以#endif 结尾的。

*   **Line control ( #line )**: Whenever we compile a program, there are chances of occurrence of some error in the program. Whenever compiler identifies error in the program it provides us with the filename in which error is found along with the list of lines and with the exact line numbers where the error is. This makes easy for us to find and rectify error.
    However we can control what information should the compiler provide during errors in compilation using the #line directive.
    **Syntax:**

    ```cpp
    #line number "filename"

    ```

    **编号**–将分配给下一个代码行的行号。从这一点开始，连续行的行号将一个接一个地增加。
    **【文件名】**–可选参数，允许重新定义将要显示的文件名。

*   **Error directive ( #error )**: This directive aborts the compilation process when it is found in the program during compilation and produces an error which is optional and can be specified as a parameter.
    **Syntax:**

    ```cpp
    #error optional_error

    ```

    这里， **optional_error** 是用户指定的任何错误，当在程序中发现该指令时，将显示该错误。
    例:

    ```cpp
    #ifndef GeeksforGeeks
    #error GeeksforGeeks not found !
    #endif  
    ```

    输出:

    ```cpp
    error: #error GeeksforGeeks not found !

    ```

**参考文献:**

*   [PPD _ better _ practice _ cs . Auckland . AC . NZ](https://www.cs.auckland.ac.nz/references/unix/digital/AQTLTBTE/DOCU_077.HTM)
*   [http://www.cplusplus.com/doc/tutorial/preprocessor/](http://www.cplusplus.com/doc/tutorial/preprocessor/)

本文由**阿玛蒂亚·兰詹·赛基亚**和**严酷的阿加瓦尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。