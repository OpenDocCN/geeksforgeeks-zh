# 功能指针在 C

> 原文:[https://www.geeksforgeeks.org/function-pointer-in-c/](https://www.geeksforgeeks.org/function-pointer-in-c/)

在 C 语言中，像[普通数据指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/) (int *，char *，等)，我们可以有指向函数的指针。下面是一个使用函数指针显示声明和函数调用的简单示例。

```cpp
#include <stdio.h>
// A normal function with an int parameter
// and void return type
void fun(int a)
{
    printf("Value of a is %d\n", a);
}

int main()
{
    // fun_ptr is a pointer to function fun() 
    void (*fun_ptr)(int) = &fun;

    /* The above line is equivalent of following two
       void (*fun_ptr)(int);
       fun_ptr = &fun; 
    */

    // Invoking fun() using fun_ptr
    (*fun_ptr)(10);

    return 0;
}
```

输出:

```cpp
Value of a is 10
```

为什么我们在函数指针周围需要一个额外的括号，比如上面例子中的 fun_ptr？
如果去掉括号，那么表达式“void (*fun_ptr)(int)”就变成了“void *fun_ptr(int)”，这是一个返回 void 指针的函数的声明。详情见以下帖子。
[如何声明函数的指针？](https://www.geeksforgeeks.org/how-to-declare-a-pointer-to-a-function/)

**下面是一些关于函数指针的有趣事实。**

**1)** 与普通指针不同，函数指针指向代码，而不是数据。通常，函数指针存储可执行代码的开始。

**2)** 与普通指针不同，我们不使用函数指针来分配或取消分配内存。

**3)** 一个函数的名字也可以用来获取函数的地址。例如，在下面的程序中，我们删除了赋值中的地址运算符“&”。我们还通过删除*改变了函数调用，程序仍然可以工作。

```cpp
#include <stdio.h>
// A normal function with an int parameter
// and void return type
void fun(int a)
{
    printf("Value of a is %d\n", a);
}

int main()
{ 
    void (*fun_ptr)(int) = fun;  // & removed

    fun_ptr(10);  // * removed

    return 0;
}
```

输出:

```cpp
Value of a is 10
```

**【4)**和普通指针一样，我们可以有一个函数指针数组。下面第 5 点中的例子显示了指针数组的语法。

**5)** 功能指针可以代替开关盒使用。例如，在下面的程序中，要求用户在 0 和 2 之间进行选择，以执行不同的任务。

```cpp
#include <stdio.h>
void add(int a, int b)
{
    printf("Addition is %d\n", a+b);
}
void subtract(int a, int b)
{
    printf("Subtraction is %d\n", a-b);
}
void multiply(int a, int b)
{
    printf("Multiplication is %d\n", a*b);
}

int main()
{
    // fun_ptr_arr is an array of function pointers
    void (*fun_ptr_arr[])(int, int) = {add, subtract, multiply};
    unsigned int ch, a = 15, b = 10;

    printf("Enter Choice: 0 for add, 1 for subtract and 2 "
            "for multiply\n");
    scanf("%d", &ch);

    if (ch > 2) return 0;

    (*fun_ptr_arr[ch])(a, b);

    return 0;
}
```

```cpp
Enter Choice: 0 for add, 1 for subtract and 2 for multiply
2
Multiplication is 150 
```

**(6)**像普通的数据指针一样，函数指针可以作为参数传递，也可以从函数返回。
例如，考虑下面的 C 程序，其中 wrapper()接收一个 void fun()作为参数，并调用传递的函数。

```cpp
// A simple C program to show function pointers as parameter
#include <stdio.h>

// Two simple functions
void fun1() { printf("Fun1\n"); }
void fun2() { printf("Fun2\n"); }

// A function that receives a simple function
// as parameter and calls the function
void wrapper(void (*fun)())
{
    fun();
}

int main()
{
    wrapper(fun1);
    wrapper(fun2);
    return 0;
}
```

这一点在 C 语言中特别有用。在 C 语言中，我们可以使用函数指针来避免代码冗余。例如，一个简单的 [qsort()](http://www.cplusplus.com/reference/cstdlib/qsort/) 函数可以用来按照升序或降序对数组进行排序，或者在数组结构的情况下按照任何其他顺序进行排序。不仅如此，通过函数指针和 void 指针，可以对任何数据类型使用 qsort。

```cpp
// An example for qsort and comparator
#include <stdio.h>
#include <stdlib.h>

// A sample comparator function that is used
// for sorting an integer array in ascending order.
// To sort any array for any other data type and/or
// criteria, all we need to do is write more compare
// functions.  And we can use the same qsort()
int compare (const void * a, const void * b)
{
  return ( *(int*)a - *(int*)b );
}

int main ()
{
  int arr[] = {10, 5, 15, 12, 90, 80};
  int n = sizeof(arr)/sizeof(arr[0]), i;

  qsort (arr, n, sizeof(int), compare);

  for (i=0; i<n; i++)
     printf ("%d ", arr[i]);
  return 0;
}
```

输出:

```cpp
5 10 12 15 80 90
```

与 qsort()类似，我们可以编写自己的函数，这些函数可以用于任何数据类型，并且可以在没有代码冗余的情况下完成不同的任务。下面是一个示例搜索函数，可用于任何数据类型。事实上，我们可以通过编写一个定制的比较函数来使用这个搜索函数来查找接近的元素(低于阈值)。

```cpp
#include <stdio.h>
#include <stdbool.h>

// A compare function that is used for searching an integer
// array
bool compare (const void * a, const void * b)
{
  return ( *(int*)a == *(int*)b );
}

// General purpose search() function that can be used
// for searching an element *x in an array arr[] of
// arr_size. Note that void pointers are used so that
// the function can be called by passing a pointer of
// any type.  ele_size is size of an array element
int search(void *arr, int arr_size, int ele_size, void *x,
           bool compare (const void * , const void *))
{
    // Since char takes one byte, we can use char pointer
    // for any type/ To get pointer arithmetic correct,
    // we need to multiply index with size of an array
    // element ele_size
    char *ptr = (char *)arr;

    int i;
    for (i=0; i<arr_size; i++)
        if (compare(ptr + i*ele_size, x))
           return i;

    // If element not found
    return -1;
}

int main()
{
    int arr[] = {2, 5, 7, 90, 70};
    int n = sizeof(arr)/sizeof(arr[0]);
    int x = 7;
    printf ("Returned index is %d ", search(arr, n,
                               sizeof(int), &x, compare));
    return 0;
}
```

输出:

```cpp
Returned index is 2
```

通过编写单独的自定义比较()，上述搜索功能可用于任何数据类型。

**7)**c++ 中很多面向对象的特性都是用 C 中的函数指针来实现的，比如[虚函数](https://www.geeksforgeeks.org/virtual-functions-and-runtime-polymorphism-in-c-set-1-introduction/)。类方法是使用函数指针实现的另一个例子。详见[本书](http://www.cs.rit.edu/~ats/books/ooc.pdf)。

**相关文章:**[C 和 C++ 中的指针|集合 1(介绍、算术和数组)](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)

**参考文献:**
[http://www . cs . CMU . edu/~ ab/15-123s 11/AnnotatedNotes/讲师 14.pdf](http://www.cs.cmu.edu/~ab/15-123S11/AnnotatedNotes/Lecture14.pdf)

[http://OCW . MIT . edu/courses/electric-engineering-and-computer-science/6-087-实用编程-in-c-January-IAP-2010/课堂讲稿/MIT6_087IAP10_lec08.pdf](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-087-practical-programming-in-c-january-iap-2010/lecture-notes/MIT6_087IAP10_lec08.pdf)

[http://www . cs . CMU . edu/~ guna/15-123s 11/讲座/讲师 14.pdf](http://www.cs.cmu.edu/~guna/15-123S11/Lectures/Lecture14.pdf)

本文由**阿沛·拉提**供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。