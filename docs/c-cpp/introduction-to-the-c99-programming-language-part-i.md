# C99 编程语言介绍:第一部分

> 原文:[https://www . geeksforgeeks . org/入门-c99-编程语言-part-i/](https://www.geeksforgeeks.org/introduction-to-the-c99-programming-language-part-i/)

**C99** 是 1999 年通过的**ISO/IEC 9899:1999**C 标准规范的别称。本文通过与 C89 标准的比较，重点介绍 C99 新增的功能。在 C99 标准的开发阶段，重新检查了 C 语言的每个元素，分析了使用模式，并预测了未来的需求。C 与 C++ 的关系为整个开发过程提供了背景。由此产生的 C99 标准是对原版优势的证明。

1.  **C99 中增加的关键词:**
    *   **[inline](https://www.geeksforgeeks.org/inline-functions-cpp/):** C99 adds the keyword inline which is applicable to functions. If we write **inline datatype function_name (param)** to any function it means that we are specifying the compiler to optimize calls to that function i.e. the function’s code will be expanded inline rather than called.

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

        **注意:**一些编译器未定义对最大值()的引用。这个内嵌特性很少用作关键字。

        上述程序相当于以下程序

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

        ```cpp
        Maximum of 5 and 10 is 10

        ```

        **Output:**

        ```cpp
        Maximum of 5 and 10 is 10

        ```

        内联函数通过维护结构化的、基于函数的方法来帮助我们创建高效的代码。

    *   **[restrict](https://www.geeksforgeeks.org/restrict-keyword-c/):** restrict is a type qualifier applicable only for pointers. A pointer qualified by restrict is initially the only means by which the object it points to can be accessed. Access to the object by another pointer can occur only if the second pointer is based on the first.

        我们使用 restrict 限定符来限制对对象的访问。这些主要用作功能参数或在 **[malloc()](https://www.geeksforgeeks.org/dynamic-memory-allocation-in-c-using-malloc-calloc-free-and-realloc/)** 中使用。限制限定符从不改变程序的语义。

    *   **_Bool Datatype:** _Bool datatype was added in C99 standard which stores 0 and 1 values. _Bool is an integer type.

        **注意:**c++ 中的 bool 关键字和 C 中的 _Bool 不同。

        _Bool 很少使用，取而代之的是 C99 定义了一个新的头文件**[【stdbool . h】](https://www.geeksforgeeks.org/bool-in-c/)**，它定义了三个宏 Bool，真和假。

    *   **_Complex:** C99 adds support for performing operations on complex numbers through _Complex and _Imaginary keywords. These keywords provide better support for numerical programming.

        **在 _Complex 中定义的类型:**

        *   浮动 _ 复杂
        *   双重复杂
        *   长双 _ 复杂
    *   **_Imaginary:** As said above, C99 adds support for performing operations on complex numbers through _Complex and _Imaginary keywords. These keywords provide better support for numerical programming.

        **复数和虚数中定义的类型:**

        *   浮点 _ 虚数
        *   双 _ 虚数
        *   长双 _ 虚数

        与布尔数据类型中讨论的相同，复数和虚数并不常用。相反，我们使用头文件**，它由内置宏**复杂的**和**假想的**宏组成。**

2.  ****添加类型限定符:**C99 中添加的另一个重要方面是引入了**长整型**和**无符号长整型**类型修饰符。long long int 的范围从–(2^63 到+(2^63。无符号长整型的最小范围是从 0 到+(2^64-1)。这种长整型允许 64 位整数作为内置类型支持。**
3.  ****阵列的变化:** C99 为阵列增加了两个重要特性:

    *   **可变长度数组:**在 C89 标准中，数组大小必须在数组声明时使用整数常量指定，并且数组大小在编译时是固定的。在 C99 标准中，我们可以声明一个数组，该数组的维度由任何整数表达式指定，这些表达式的值在运行时是已知的。这被称为**可变长度阵列(VLA)** 。
    *   **Inclusion of Type Qualifiers:** In C99, we can use the keyword **[static](https://www.geeksforgeeks.org/static-keyword-cpp/)** inside the square brackets during array declaration. This is only applied when array is declared in function parameters i.e

        **示例:**

        ```cpp
        int fun1(char arr[static 80])
        {
            // code
        }
        ```

        在上面的例子中，arr 总是指向一个 80 个元素的数组，也就是说 arr 保证指向包含至少 80 个元素的字符数组的起始元素。如果在函数参数中声明了该数组，我们还可以在方括号内使用关键字 [restrict](https://www.geeksforgeeks.org/restrict-keyword-c/) 、 [volatile](https://www.geeksforgeeks.org/understanding-volatile-qualifier-in-c/) 和 [const](https://www.geeksforgeeks.org/const-qualifier-in-c/) 。关键字**限制**指定指针是访问对象的唯一初始方式。 **const** 表示指针始终指向同一个对象。**挥发**是允许的，但没有意义。

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

        ```cpp
        2 3 4 5 5 5 5 5 6 6

        ```** 
4.  ****Single Line Comments:** Single Line comments aren’t accepted in C89 standard. C99 standard introduces Single Line Comments which are used only when brief remarks are needed. These comments begin with **//** and runs to the end of the line.

    例如:

    ```cpp
    // First Comment
    int a; // another comment
    ```** 
5.  ****Declaration of Identifiers:**
    According to the C89 standard, all Identifiers should be declared at the start of the code block. If we need any other identifier at the middle, we can’t declare for that instance or time. We need to declare that at the start. C99 has changed this rule as we can declare identifiers whenever we need in a code.

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

    **Output:****