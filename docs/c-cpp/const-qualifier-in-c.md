# C

中的常量限定符

> 原文:[https://www.geeksforgeeks.org/const-qualifier-in-c/](https://www.geeksforgeeks.org/const-qualifier-in-c/)

限定符 const 可以应用于任何变量的声明，以指定其值不会被更改(这取决于 const 变量的存储位置，我们可以通过使用指针来更改 const 变量的值)。如果试图更改常量，结果是实现定义的。
**1)指向变量的指针。**T3】

## C

```cpp
int *ptr;
```

我们可以改变 ptr 的值，也可以改变指向的对象 ptr 的值。指针和指针指向的值都存储在读写区。请参见下面的代码片段。

## C

```cpp
#include <stdio.h>
int main(void)
{
    int i = 10;
    int j = 20;
    int *ptr = &i;
    /* pointer to integer */
    printf("*ptr: %d\n", *ptr);

    /* pointer is pointing to another variable */
    ptr = &j;
    printf("*ptr: %d\n", *ptr);

    /* we can change value stored by pointer */
    *ptr = 100;
    printf("*ptr: %d\n", *ptr);

    return 0;
}
```

**输出:**

```cpp
    *ptr: 10
    *ptr: 20
    *ptr: 100
```

**2)指针指向常数。**
指向常量的指针可以通过以下两种方式声明。

## C

```cpp
const int *ptr;
```

或者

## C

```cpp
int const *ptr;
```

我们可以改变指针指向任何其他整数变量，但不能改变指针 ptr 指向的对象(实体)的值。指针存储在读写区(本例中为堆栈)。指向的对象可能在只读或读写区域。让我们看看下面的例子。

## C

```cpp
#include <stdio.h>
int main(void)
{
    int i = 10;  
    int j = 20;
    /* ptr is pointer to constant */
    const int *ptr = &i;   

    printf("ptr: %d\n", *ptr);
    /* error: object pointed cannot be modified
    using the pointer ptr */   
    *ptr = 100;

    ptr = &j;          /* valid */
    printf("ptr: %d\n", *ptr);

    return 0;
}
```

**输出:**

```cpp
 error: assignment of read-only location ‘*ptr’
```

下面是另一个例子，其中变量 I 本身是常数。

## C

```cpp
#include <stdio.h>

int main(void)
{ 
    /* i is stored in read only area*/
    int const i = 10;   
    int j = 20;

    /* pointer to integer constant. Here i
    is of type "const int", and &i is of
    type "const int *".  And p is of type
    "const int", types are matching no issue */
    int const *ptr = &i;       

    printf("ptr: %d\n", *ptr);

    /* error */
    *ptr = 100;       

    /* valid. We call it up qualification. In
    C/C++, the type of "int *" is allowed to up
    qualify to the type "const int *". The type of
    &j is "int *" and is implicitly up qualified by
    the compiler to "const int *" */

    ptr = &j;         
    printf("ptr: %d\n", *ptr);

    return 0;
}
```

**输出:**

```cpp
 error: assignment of read-only location ‘*ptr’
```

在 C++ 中不允许向下限定，这可能会在 C 中导致警告。下面是另一个带有向下限定的示例。

## C

```cpp
#include <stdio.h>

int main(void)
{
    int i = 10;
    int const j = 20;

    /* ptr is pointing an integer object */
    int *ptr = &i;

    printf("*ptr: %d\n", *ptr);

    /* The below assignment is invalid in C++, results in error
       In C, the compiler *may* throw a warning, but casting is
       implicitly allowed */
    ptr = &j;

    /* In C++, it is called 'down qualification'. The type of expression
       &j is "const int *" and the type of ptr is "int *". The
       assignment "ptr = &j" causes to implicitly remove const-ness
       from the expression &j. C++ being more type restrictive, will not
       allow implicit down qualification. However, C++ allows implicit
       up qualification. The reason being, const qualified identifiers
       are bound to be placed in read-only memory (but not always). If
       C++ allows above kind of assignment (ptr = &j), we can use 'ptr'
       to modify value of j which is in read-only memory. The
       consequences are implementation dependent, the program may fail
       at runtime. So strict type checking helps clean code. */

    printf("*ptr: %d\n", *ptr);

    return 0;
}

// Reference:
// http://www.dansaks.com/articles/1999-02%20const%20T%20vs%20T%20const.pdf

// More interesting stuff on C/C++ @ http://www.dansaks.com/articles.shtml
```

**3)变量的常量指针。**

## C

```cpp
int *const ptr;
```

上面的声明是一个指向整数变量的常量指针，意味着我们可以改变指针所指向的对象的值，但是不能改变指针指向另一个变量。

## C

```cpp
#include <stdio.h>

int main(void)
{
   int i = 10;
   int j = 20;
/* constant pointer to integer */
   int *const ptr = &i;   

   printf("ptr: %d\n", *ptr);

   *ptr = 100;    /* valid */
   printf("ptr: %d\n", *ptr);

   ptr = &j;        /* error */
   return 0;
}
```

输出:

```cpp
 error: assignment of read-only variable ‘ptr’
```

**4)常数指针指向常数**

## C

```cpp
const int *const ptr;
```

上面的声明是一个指向常量变量的常量指针，这意味着我们不能改变指针所指向的值，也不能将指针指向其他变量。让我们用一个例子来看看。

## C

```cpp
#include <stdio.h>

int main(void)
{
    int i = 10;
    int j = 20;
/* constant pointer to constant integer */
    const int *const ptr = &i;       

    printf("ptr: %d\n", *ptr);

    ptr = &j;     /* error */
    *ptr = 100;   /* error */

    return 0;
}
```

输出:

```cpp
     error: assignment of read-only variable ‘ptr’
     error: assignment of read-only location ‘*ptr’
```

总结:

<figure class="table">ptr **无**

| Type | **Declaration** | **指针值变化****(* ptr = 100)** | **指针值变化****(ptr =&a)** |
| **is** | **is** |
| **2) The pointer points to the constant** | 

*   int const * ptr

 | t69〔const ptr〕 | **is** | **No** |
| **4) const pointer pointing constant** | **const int * const ptr** | without |

</figure>

本文由**纳伦德拉·康拉尔卡尔**整理。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。