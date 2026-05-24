# 在 C/C++ 中访问数组越界

> 原文:[https://www.geeksforgeeks.org/accessing-array-bounds-ccpp/](https://www.geeksforgeeks.org/accessing-array-bounds-ccpp/)

额外条件:[C/c++ 中的数组](https://www.geeksforgeeks.org/arrays-in-c-language-set-1-introduction/)

在高级语言如 Java 中，有一些函数通过生成一个异常如 Java . lang . arrayindexoutofboundsexception 来防止你访问数组越界，但是在 C 语言中，没有这样的功能，所以程序员需要处理这种情况。

**如果程序员不小心访问了数组的任何超出界限的索引怎么办？**

不要提供任何规范来处理访问无效索引的问题。根据国际标准化组织标准，它被称为**未定义行为**。
未定义行为(UB)是执行计算机代码的结果，对于程序的当前状态(例如内存)，其行为不是由代码可以遵守的语言规范规定的。这通常发生在源代码的翻译者做出某些假设时，但是这些假设在执行过程中没有得到满足。

**访问数组越界时的未定义行为示例**

1.  **Access non allocated location of memory:** The program can access some piece of memory which is owned by it.

    ```cpp
    // Program to demonstrate 
    // accessing array out of bounds
    #include <stdio.h>
    int main()
    {
        int arr[] = {1,2,3,4,5};
        printf("arr [0] is %d\n", arr[0]);

        // arr[10] is out of bound
        printf("arr[10] is %d\n", arr[10]);
        return 0;
    }
    ```

    输出:

    ```cpp
    arr [0] is 1
    arr[10] is -1786647872

    ```

    这里可以观察到，arr[10]正在访问包含垃圾值的存储单元。

2.  **Segmentation fault:** The program can access some piece of memory which is not owned by it, which can cause crashing of program such as segmentation fault.

    ```cpp
    // Program to demonstrate 
    // accessing array out of bounds
    #include <stdio.h>
    int main()
    {
        int arr[] = {1,2,3,4,5};
        printf("arr [0] is %d\n",arr[0]);
        printf("arr[10] is %d\n",arr[10]);

        // allocation memory to out of bound 
        // element
        arr[10] = 11;
        printf("arr[10] is %d\n",arr[10]);
        return 0;
    }
    ```

    输出:
    运行时错误:分段故障(SIGSEGV)

**要点:**

*   在 C 编程中，当使用数组时，保持在数组的边界内，以避免任何这样的错误。
*   然而，C++ 提供了 [std::vector](https://www.geeksforgeeks.org/vector-in-cpp-stl/) 类模板，它不需要执行边界检查。向量也有[标准::at()](https://www.geeksforgeeks.org/stdbasic_stringat/) 成员函数，可以执行边界检查。

本文由 **[曼德普·辛格](https://github.com/msdeep14)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。