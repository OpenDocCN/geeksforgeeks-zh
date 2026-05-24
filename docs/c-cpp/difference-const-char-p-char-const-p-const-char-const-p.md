# 常量 char *p、char * const p 和常量 char * const p 的区别

> 哎哎哎:# t0]https://www . geeksforgeeks . org/difference-const-char-p-const-p-const-char-const-p/

先决条件:[指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)
当 char、const、* p 都用在不同的排列中，含义根据放在哪里而变化时，会有很多混淆。下面的文章重点介绍所有这些的区别和用法。
限定符 [const](https://www.geeksforgeeks.org/const-qualifier-in-c/) 可以应用于任何变量的声明，以指定其值不会改变。const 关键字适用于其左侧的任何内容。如果它的左边没有任何东西，它就适用于它右边的任何东西。

**1。const char *ptr :** 这是一个指向常量字符的指针。**你不能改变 ptr 指向的值，但是你可以改变指针本身**。“const char *”是指向 const char 的(非常数)指针。

## C

```cpp
// C program to illustrate
// char const *p
#include<stdio.h>
#include<stdlib.h>

int main()
{
    char a ='A', b ='B';
    const char *ptr = &a;

    //*ptr = b; illegal statement (assignment of read-only location *ptr)

    // ptr can be changed
    printf( "value pointed to by ptr: %c\n", *ptr);
    ptr = &b;
    printf( "value pointed to by ptr: %c\n", *ptr);
}
```

1.  输出:

```cpp
value pointed to by ptr:A
value pointed to by ptr:B
```

**注意:**在**常量 char *p 和 char 常量*p** 之间没有区别，因为两者都指向一个常量 char，并且‘*(星号)的位置也是相同的。

**2。char *const ptr :** 这是一个指向非常数字符的常量指针。**你不能改变指针 p，但是可以改变 ptr 指向的值。**

## C

```cpp
// C program to illustrate
// char* const p
#include<stdio.h>
#include<stdlib.h>

int main()
{
    char a ='A', b ='B';
    char *const ptr = &a;
    printf( "Value pointed to by ptr: %c\n", *ptr);
    printf( "Address ptr is pointing to: %d\n\n", ptr);

    //ptr = &b; illegal statement (assignment of read-only variable ptr)

    // changing the value at the address ptr is pointing to
    *ptr = b;
    printf( "Value pointed to by ptr: %c\n", *ptr);
    printf( "Address ptr is pointing to: %d\n", ptr);
}
```

输出:

```cpp
Value pointed to by ptr: A
Address ptr is pointing to: -1443150762

Value pointed to by ptr: B
Address ptr is pointing to: -1443150762
```

**注意:**指针始终指向同一个地址，只有该位置的值发生变化。

**3。const char * const ptr :** 这是一个指向常量字符的常量指针。**你既不能改变指针指向的数值，也不能改变指针指向的数值。**

## C

```cpp
// C program to illustrate
//const char * const ptr
#include<stdio.h>
#include<stdlib.h>

int main()
{
    char a ='A', b ='B';
    const char *const ptr = &a;

    printf( "Value pointed to by ptr: %c\n", *ptr);
    printf( "Address ptr is pointing to: %d\n\n", ptr);

    // ptr = &b; illegal statement (assignment of read-only variable ptr)
    // *ptr = b; illegal statement (assignment of read-only location *ptr)

}
```

输出:

```cpp
Value pointed to by ptr: A
Address ptr is pointing to: -255095482
```

**注:char const * const ptr** 与 **const char *const ptr** 相同。
[const 关键字测验](https://www.geeksforgeeks.org/c-plus-plus-gq/const-keyword-gq/)

本文由**雅什辛拉**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。