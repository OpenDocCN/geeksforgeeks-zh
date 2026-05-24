# C/c++ 中的空指针

> 原文:[https://www.geeksforgeeks.org/void-pointer-c-cpp/](https://www.geeksforgeeks.org/void-pointer-c-cpp/)

void 指针是一个没有关联数据类型的指针。void 指针可以保存任何类型的地址，并且可以被类型化为任何类型。

```cpp
int a = 10;
char b = 'x';

void *p = &a;  // void pointer holds address of int 'a'
p = &b; // void pointer holds address of char 'b'
```

**void 指针的优点:**
**1)** malloc()和 calloc()返回 void *类型，这允许这些函数用于分配任何数据类型的内存(仅仅因为 void *)

```cpp
int main(void)
{
    // Note that malloc() returns void * which can be 
    // typecasted to any type like int *, char *, ..
    int *x = malloc(sizeof(int) * n);
}
```

注意，上面的程序是用 C 编译的，而不是用 C++ 编译的。在 C++ 中，我们必须显式地将 malloc 的返回值类型转换为(int *)。

**2)**C 中的 void 指针用于实现 C 中的泛型函数，例如 qsort() 中使用的[比较函数。](https://www.geeksforgeeks.org/comparator-function-of-qsort-in-c/)

**一些有趣的事实:**
**1)** 无效指针不能被取消引用。例如，以下程序不编译。

```cpp
#include<stdio.h>
int main()
{
    int a = 10;
    void *ptr = &a;
    printf("%d", *ptr);
    return 0;
}
```

输出:

```cpp
Compiler Error: 'void*' is not a pointer-to-object type 
```

以下程序编译并运行良好。

```cpp
#include<stdio.h>
int main()
{
    int a = 10;
    void *ptr = &a;
    printf("%d", *(int *)ptr);
    return 0;
}
```

输出:

```cpp
10
```

**2)**[C 标准](https://www.geeksforgeeks.org/c-programming-language-standard/)不允许使用空指针进行指针运算。然而，在 GNU C 中，考虑到空隙的大小是 1，这是允许的。例如，下面的程序在 gcc 中编译并运行良好。

```cpp
#include<stdio.h>
int main()
{
    int a[2] = {1, 2};
    void *ptr = &a;
    ptr = ptr + sizeof(int);
    printf("%d", *(int *)ptr);
    return 0;
}
```

输出:

```cpp
2
```

请注意，上述程序可能无法在其他编译器中工作。

**参考文献:**
[http://stackoverflow . com/questions/20967868/应该-编译器-指针警告-带空指针的算术](http://stackoverflow.com/questions/20967868/should-the-compiler-warn-on-pointer-arithmetic-with-a-void-pointer)
[http://stackoverflow . com/questions/692564/c 程序设计中的空指针概念](http://stackoverflow.com/questions/692564/concept-of-void-pointer-in-c-programming)

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论