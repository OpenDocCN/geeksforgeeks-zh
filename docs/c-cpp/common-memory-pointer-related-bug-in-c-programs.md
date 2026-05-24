# C 程序中常见的内存/指针相关错误

> 原文:[https://www . geesforgeks . org/common-memory-pointer-related-bug-in-c-programs/](https://www.geeksforgeeks.org/common-memory-pointer-related-bug-in-c-programs/)

**解除对未知内存位置的引用** : C 程序员大多使用 scanf()函数进行输入，但有时一个小小的错误就可能带来 bug 甚至使整个程序崩溃。
scanf()的语法是 **scanf("%d "，&a)；**。可能会遗漏一个&并将 **& a 写成一个**所以现在 **scanf("%d "，a)；**取消对未知位置的引用。
现在，程序可能会因异常而终止，或者它可能对应于一个有效位置(与当前程序无关，但与某个其他程序相关)，并且可能会被覆盖，这可能会在以后导致未知的影响。

```cpp
// A C program to demonstrate that missing
// an & in scanf() may cause memory problems.
#include <stdio.h>

int main()
{
    int a;
    scanf("%d", a);
    printf("%d", a);
    return 0;
}
```

**读取未初始化的内存。**在 C 语言中，初学者通常使用 malloc()来提供运行时内存，但是使用 malloc()时，内存块不会被初始化，可以访问。

```cpp
// A C program to demonstrate that missing
// an & may cause memory problems.
#include <stdio.h>

int main()
{
    int* p = (int*)malloc(sizeof(int) * 4);
    int i;

    // p[] contains some garbage value so
    // below loop does not make any sense.
    for (i = 0; i < 4; i++)
        p[i] += 100;
}
```

一种解决方案是使用 calloc()来代替，它将块初始化为 0。

**缓冲区溢出:**这是 C 语言中非常常见的错误，由于 C 语言本身存在一个错误的函数，即 get()函数，该函数用于将字符串作为输入，这种错误变得更加常见。它不检查程序中用于存储字符串的内存，因此，如果用户输入更大的字符串，将会得到()并覆盖字符串后的内存位置，从而导致溢出。

```cpp
void read()
{
    char str[20];
    gets(str);
    printf("%s", str);
    return;
}
```

代码遭受缓冲区溢出，因为 get()没有进行任何数组绑定测试。get()继续读取，直到看到换行符。为了避免缓冲区溢出，应该使用 f gets()而不是 get()，因为 fgets()确保读取的字符不超过 MAX_LIMIT。

```cpp
#define MAX_LIMIT 20
void read()
{
    char str[MAX_LIMIT];
    fgets(str, MAX_LIMIT, stdin);
    printf("%s", str);
    return;
}
```

**内存泄漏**当使用的堆内存没有被取消分配时，就会出现这种情况，由于这种情况，主内存最终会被填满，空闲内存会变少。

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

如果不再使用内存，我们应该在 malloc()之后使用 free()。

```cpp
/* Function without memory leak */
#include <stdlib.h>

void f()
{
    int* ptr = (int*)malloc(sizeof(int));

    /* Do some work */

    free(ptr); // Deallocate memory
    return;
}
```

**由于优先级而导致的错误**对运算符及其优先级的理解不足会导致错误，尤其是像

```cpp
// C program to demonstrate bug introduced due
// to precedence.
#include <stdlib.h>

int demo()
{
    int a = 10;
    int* p = &a;

    // intention was to increase the value of a
    *p++ ;
}
```

***(取消引用/间接运算符不是乘法)和后缀++** 的优先级不同，但是前缀+++ 和*具有相同的优先级，因此，首先 p 的值将增加，并将指向一个坏的内存区域，然后取消引用，并将覆盖该位置，否则程序可能会终止。详见【】++*p、*p++ 与* +++ p 的区别。

**不存在变量的发送地址**局部变量的返回地址导致问题，

```cpp
#include <stdlib.h>

int fun()
{
    int x = 10;
    return &x;
}
int main()
{
    int* p = fun();
    *p = 20;
}
```

当函数 fun()被调用时，变量 a 被创建，但是一旦函数返回，它就会被销毁。由于函数被返回，它的地址 p 将指向堆栈区域中的一个存储区域，如果调用另一个函数，那么指针 **p** 的改变可能导致错误。

**指针算法**指针算法可能会令人困惑，让我们举个例子，假设整数是 4 字节。

```cpp
int main()
{
    int x[10] = { 0 }, i = 0, *p;

    // p point to starting address of array x
    p = &x[0];
    while (i < 10) {
        *p = 10;

        // intention was to point to integer at x[1]
        p = p + 4;
        i++ ;
    }
}
```

虽然它看起来是正确的，因为整数是 4 字节，p 在起始位置，所以加 4 会导致 p 指向数组 n 中的下一个整数，但是指针算术是根据其数据类型的大小工作的，所以加 1 到整数指针，然后 sizeof(int)会被加到它上面，这同样适用于指向任何其他数据类型的指针。

```cpp
int main()
{
    int x[10] = { 0 }, i = 0, *p;
    p = &x[0]; // p point to starting address of array x
    while (i < 10) {
        *p = 10;
        p++ ; // means p = p + sizeof(int)
        i++ ;
    }
}
```

**将数组作为参数传递**当我们将数组传递给函数时，它总是被当作函数中的指针。这就是为什么我们不应该在数组参数上使用 sizeof。我们应该始终将大小作为第二个参数。

```cpp
#include <stdio.h>

// arr is a pointer even if we have
// use square brackets.
void printArray(int arr[])
{
    int i;

    /* sizeof should not be used here to get number 
    of elements in array*/
    int arr_size = sizeof(arr) / sizeof(arr[0]); 
    for (i = 0; i < arr_size; i++) {
        printf("%d ", arr[i]);
    }
}

int main()
{
    int arr[4] = { 1, 2, 3, 4 };
    printArray(arr);
    return 0;
}
```

以下是更正后的代码

```cpp
#include <stdio.h>

// arr is a pointer even if we have
// use square brackets.
void printArray(int arr[], int arr_size)
{
    int i;
    for (i = 0; i < arr_size; i++) {
        printf("%d ", arr[i]);
    }
}

int main()
{
    int arr[] = { 1, 2, 3, 4 };
    int arr_size = sizeof(arr) / sizeof(arr[0]); 
    printArray(arr, arr_size);
    return 0;
}
```

**参考:**
[计算机系统:程序员的视角](https://www.geeksforgeeks.org/difference-between-p-p-and-p/)