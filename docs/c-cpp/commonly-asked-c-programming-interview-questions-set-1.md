# 常见 C 编程面试问题|第一套

> 原文:[https://www . geesforgeks . org/common-question-c-programming-interview-questions-set-1/](https://www.geeksforgeeks.org/commonly-asked-c-programming-interview-questions-set-1/)

**变量/函数的声明和定义有什么区别**
**Ans:** 变量/函数的声明只是声明变量/函数存在于程序的某个地方，但是没有为它们分配内存。但是变量/函数的声明起着重要的作用。这就是变量/函数的类型。因此，当一个变量被声明时，程序知道该变量的数据类型。在函数声明的情况下，程序知道函数的参数是什么，它们的数据类型，参数的顺序和函数的返回类型。所以这就是宣言。说到定义，当我们定义一个变量/函数时，除了声明的作用，它还为该变量/函数分配内存。因此，我们可以把定义看作是一组超级声明。(或作为定义子集的声明)。

> //这只是声明。y 不是这个语句
> external int y 分配的内存；
> 
> //这既是声明也是定义，给 x 的内存就是通过这个语句分配的。
> int x；

**C 中有哪些不同的存储类说明符？**
**Ans:** 自动、注册、静态、外部

**变量的范围是什么？变量在 [C](https://www.geeksforgeeks.org/c/) 中的作用域是怎样的？**
**Ans:** 变量的作用域是程序中变量可以直接访问的部分。在 C 语言中，所有标识符都是词汇(或静态)范围的。详见[本](https://www.geeksforgeeks.org/scope-rules-in-c/)。

**没有分号怎么打印《你好世界》？**
**Ans:**

```cpp
#include <stdio.h>
int main(void)
{
    if (printf("Hello World")) {
    }
}
```

参见[打印“极客为极客”，答案不用分号](https://www.geeksforgeeks.org/write-a-c-program-to-print-geeks-for-geeks-without-using-a-semicolon/)。

**什么时候应该在 C 程序中使用指针？**
**1。**获取一个变量的地址
***2。**为了实现 C 语言中的引用传递:*指针允许不同的函数共享和修改它们的局部变量。
***3。**通过大型结构*可以避免结构的完全复制。
***4。**实现类似链表和二叉树的“链接”数据结构*。

**什么是空指针？**
**Ans:** NULL 用于表示指针没有指向有效位置。理想情况下，如果在声明时不知道指针的值，我们应该将指针初始化为空。此外，当指针所指向的内存在程序中间被释放时，我们应该使指针为空。

**什么是悬空指针？**
**Ans:** 悬空指针是不指向有效内存位置的指针。当一个对象被删除或解除分配，而不修改指针的值，使得指针仍然指向解除分配的内存的内存位置时，悬空指针就出现了。以下是一些例子。

```cpp
// EXAMPLE 1
int* ptr = (int*)malloc(sizeof(int));
..........................free(ptr);

// ptr is a dangling pointer now and operations like following are invalid
*ptr = 10; // or printf("%d", *ptr);
```

```cpp
// EXAMPLE 2
int* ptr = NULL
{
    int x = 10;
    ptr = &x;
}
// x goes out of scope and memory allocated to x is free now.
// So ptr is a dangling pointer now.
```

**什么是内存泄漏？为什么要避免**
**Ans:** 当程序员在堆中创建一个内存却忘记删除它时，就会发生内存泄漏。对于守护程序和服务器这样的程序来说，内存泄漏是一个特别严重的问题，顾名思义，它们永远不会终止。

```cpp
/* Function with memory leak */
#include <stdlib.h>

void f()
{
    int* ptr = (int*)malloc(sizeof(int));

    /* Do some work */

    return; /* Return without freeing ptr*/
}
```

**什么是局部静态变量？它们有什么用？**
**Ans:** 局部静态变量是一个变量，它的生命周期不会以声明它的函数调用结束。它延长了整个程序的生命周期。对该函数的所有调用共享本地静态变量的相同副本。静态变量可以用来计算函数被调用的次数。此外，静态变量的默认值为 0。例如，以下程序打印“0 1”

```cpp
#include <stdio.h>
void fun()
{
    // static variables get the default value as 0.
    static int x;
    printf("%d ", x);
    x = x + 1;
}

int main()
{
    fun();
    fun();
    return 0;
}
// Output: 0 1
```

**什么是静态函数？它们有什么用？**
**Ans:** 在 C 语言中，函数默认是全局的。函数名前的“static”关键字使其成为静态的。与 C 语言中的全局函数不同，对静态函数的访问仅限于声明它们的文件。因此，当我们想要限制对函数的访问时，我们将它们设为静态。使函数成为静态的另一个原因是可以在其他文件中重用相同的函数名。详见[本](https://www.geeksforgeeks.org/what-are-static-functions-in-c/)示例。

*   [常见 C 编程面试问题|第二集](https://www.geeksforgeeks.org/commonly-asked-c-programming-interview-questions-set-2/)
*   练习 C 上的[测验](https://www.geeksforgeeks.org/quiz-corner-gq/)
*   C [篇](https://www.geeksforgeeks.org/c/)

你可能还喜欢:

[常见 C 编程面试问题|第 2 集](https://www.geeksforgeeks.org/commonly-asked-c-programming-interview-questions-set-2/ "Permanent link to Commonly Asked C Programming Interview Questions | Set 2")
[常见 Java 编程面试问题|第 1 集](https://www.geeksforgeeks.org/commonly-asked-java-programming-interview-questions-set-1/ "Permanent link to Commonly Asked Java Programming Interview Questions | Set 1")
[亚马逊最常问的面试问题](https://www.geeksforgeeks.org/amazon-interview-questions/)
[微软最常问的面试问题](https://www.geeksforgeeks.org/microsofts-asked-interview-questions/ "Permanent link to Microsoft’s most asked interview questions")
[埃森哲最常问的面试问题](https://www.geeksforgeeks.org/accentures-most-asked-technical-interview-questions/ "Permanent link to Accenture’s most asked Interview Questions")
[常见 OOP 面试问题](https://www.geeksforgeeks.org/commonly-asked-oop-interview-questions/ "Permanent link to Commonly Asked OOP Interview Questions | Set 1")
[常见 C++ 面试问题](https://www.geeksforgeeks.org/commonly-asked-c-interview-questions-set-1/ "Permanent link to Commonly Asked C++ Interview Questions | Set 1")
T21】常见 DBMS 面试问题| 集合 1
[常见的 DBMS 面试问题|集合 2](https://www.geeksforgeeks.org/commonly-asked-dbms-interview-questions-set-2/)
[常见的操作系统面试问题|集合 1](https://www.geeksforgeeks.org/commonly-asked-operating-systems-interview-questions-set-1/)
[常见的数据结构面试问题。](https://www.geeksforgeeks.org/commonly-asked-data-structure-interview-questions-set-1/ "Permanent link to Commonly Asked Data Structure Interview Questions | Set 1")
[常见算法面试问题](https://www.geeksforgeeks.org/commonly-asked-algorithm-interview-questions-set-1/)
[常见计算机网络面试问题](https://www.geeksforgeeks.org/commonly-asked-computer-networks-interview-questions-set-1/)
[面试问题前 10 名算法](https://www.geeksforgeeks.org/top-10-algorithms-in-interview-questions/)

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。