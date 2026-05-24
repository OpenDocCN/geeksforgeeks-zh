# 悬空、无效、空和野指针

> 原文:[https://www . geesforgeks . org/悬空-void-null-wild-pointers/](https://www.geeksforgeeks.org/dangling-void-null-wild-pointers/)

****悬空指针****

指向已被删除(或释放)的内存位置的指针称为悬空指针。指针作为悬空指针有三种不同的方式

1.  **解除内存分配**

    ```cpp
    // Deallocating a memory pointed by ptr causes
    // dangling pointer
    #include <stdlib.h>
    #include <stdio.h>
    int main()
    {
        int *ptr = (int *)malloc(sizeof(int));

        // After below free call, ptr becomes a 
        // dangling pointer
        free(ptr); 

        // No more a dangling pointer
        ptr = NULL;
    }
    ```

2.  **Function Call**

    ```cpp
    // The pointer pointing to local variable becomes
    // dangling when local variable is not static.
    #include<stdio.h>

    int *fun()
    {
        // x is local variable and goes out of
        // scope after an execution of fun() is
        // over.
        int x = 5;

        return &x;
    }

    // Driver Code
    int main()
    {
        int *p = fun();
        fflush(stdin);

        // p points to something which is not
        // valid anymore
        printf("%d", *p);
        return 0;
    }
    ```

    输出:

    ```cpp
    A garbage Address

    ```

    如果 x 是静态变量，上面的问题就不会出现(或者 p 不会变得悬空)。

    ```cpp
    // The pointer pointing to local variable doesn't
    // become dangling when local variable is static.
    #include<stdio.h>

    int *fun()
    {
        // x now has scope throughout the program
        static int x = 5;

        return &x;
    }

    int main()
    {
        int *p = fun();
        fflush(stdin);

        // Not a dangling pointer as it points
        // to static variable.
        printf("%d",*p);
    }
    ```

    输出:

    ```cpp
     5
    ```

3.  **变量超出范围**

    ```cpp
    void main()
    {
       int *ptr;
       .....
       .....
       {
           int ch;
           ptr = &ch;
       } 
       .....   
       // Here ptr is dangling pointer
    }

    ```

**[虚空指针](https://www.geeksforgeeks.org/void-pointer-c-cpp/)**

Void 指针是一种特定的指针类型-void *-指向存储中某个数据位置的指针，它没有任何特定的类型。Void 指的是类型。基本上，它指向的数据类型可以是任何类型。如果我们将字符数据类型的地址分配给 void 指针，它将变成字符指针，如果是 int 数据类型，则变成 int 指针，依此类推。任何指针类型都可以转换为空指针，因此它可以指向任何值。
**重要点**

1.  无效指针**不能被取消引用**。然而，这可以通过类型转换 void 指针来完成
2.  由于缺少具体值和大小，指针算术在空指针上是不可能的。

**示例:**

```cpp
#include<stdlib.h>

int main()
{
    int x = 4;
    float y = 5.5;

    //A void pointer
    void *ptr;
    ptr = &x;

    // (int*)ptr - does type casting of void 
    // *((int*)ptr) dereferences the typecasted 
    // void pointer variable.
    printf("Integer variable is = %d", *( (int*) ptr) );

    // void pointer is now float
    ptr = &y; 
    printf("\nFloat variable is= %f", *( (float*) ptr) );

    return 0;
}
```

输出:

```cpp
Integer variable is = 4
Float variable is= 5.500000
```

详见[作废指针篇](https://www.geeksforgeeks.org/void-pointer-c-cpp/)。

**[空指针](https://www.geeksforgeeks.org/few-bytes-on-null-pointer-in-c/)**

空指针是不指向任何东西的指针。在这种情况下，如果我们没有分配给指针的地址，那么我们可以简单地使用空值。

```cpp
#include <stdio.h>
int main()
{
    // Null Pointer
    int *ptr = NULL;

    printf("The value of ptr is %p", ptr);
    return 0;
}
```

输出:

```cpp
The value of ptr is (nil)

```

**重要点**

1.  **空指针与未初始化指针–**未初始化指针存储未定义的值。空指针存储一个已定义的值，但该值被环境定义为不是任何成员或对象的有效地址。
2.  **空指针 vs 空指针**–空指针是一个值，而空指针是一个类型

**[野指针](https://www.geeksforgeeks.org/what-are-wild-pointers-how-can-we-avoid/)**

一个没有被初始化为任何东西(甚至不是空值)的指针被称为野指针。指针可能被初始化为非空垃圾值，该值可能不是有效地址。

```cpp
int main()
{
    int *p;  /* wild pointer */

    int x = 10;

    // p is not a wild pointer now
    p = &x;

    return 0;
}
```

本文由 **Spoorthi Arun** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。