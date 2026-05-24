# 指针在 C/C++ 中的应用

> 原文:[https://www . geesforgeks . org/applications-of-pointers-in-c-CPP/](https://www.geeksforgeeks.org/applications-of-pointers-in-c-cpp/)

前提条件:[C/c++ 中的指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)，[C 程序的内存布局](https://www.geeksforgeeks.org/memory-layout-of-c-program/)。

*   **通过引用传递参数**。通过引用传递有两个目的

(一)**修改其他函数的变量。**交换两个变量的例子；

## C

```cpp
// C program to demonstrate that we can change
// local values of one function in another using pointers.

#include <stdio.h>

void swap(int* x, int* y)
{
    int temp = *x;
    *x = *y;
    *y = temp;
}

int main()
{
    int x = 10, y = 20;
    swap(&x, &y);
    printf("%d %d\n", x, y);
    return 0;
}
```

## C++

```cpp
// C++ program to demonstrate that we can change
// local values of one function in another using
// pointers.
#include <iostream>
using namespace std;

void swap(int* x, int* y)
{
    int temp = *x;
    *x = *y;
    *y = temp;
}

int main()
{
    int x = 10, y = 20;
    swap(&x, &y);
    cout << x << " " << y << endl;
    return 0;
}
```

输出:

```cpp
20 10
```

(二)**出于效率目的**。示例在没有引用的情况下传递大型结构会创建该结构的副本(因此会浪费空间)。
注:以上两个也可以通过 C++ 中的[引用来实现。](https://www.geeksforgeeks.org/references-in-c/) 

*   **用于访问数组元素。**编译器内部使用指针访问数组元素。

## C

```cpp
// C program to demonstrate that compiler
// internally uses pointer arithmetic to access
// array elements.

#include <stdio.h>

int main()
{
    int arr[] = { 100, 200, 300, 400 };

    // Compiler converts below to *(arr + 2).
    printf("%d ", arr[2]);

    // So below also works.
    printf("%d\n", *(arr + 2));

    return 0;
}
```

## C++

```cpp
// C++ program to demonstrate that compiler
// internally uses pointer arithmetic to access
// array elements.
#include <iostream>
using namespace std;

int main()
{
    int arr[] = { 100, 200, 300, 400 };

    // Compiler converts below to *(arr + 2).
    cout << arr[2] << " ";

    // So below also works.
    cout << *(arr + 2) << " ";

    return 0;
}
```

输出:

```cpp
300 300
```

*   **返回多个值。**返回数字的平方和平方根的示例。

## C

```cpp
// C program to demonstrate that using a pointer
// we can return multiple values.

#include <math.h>
#include <stdio.h>

void fun(int n, int* square, double* sq_root)
{
    *square = n * n;
    *sq_root = sqrt(n);
}

int main()
{

    int n = 100;
    int sq;
    double sq_root;
    fun(n, &sq, &sq_root);

    printf("%d %f\n", sq, sq_root);
    return 0;
}
```

## C++

```cpp
// C++ program to demonstrate that using a pointer
// we can return multiple values.
#include <bits/stdc++.h>
using namespace std;

void fun(int n, int* square, double* sq_root)
{
    *square = n * n;
    *sq_root = sqrt(n);
}

int main()
{

    int n = 100;
    int* sq = new int;
    double* sq_root = new double;
    fun(n, sq, sq_root);
    cout << *sq << " " << *sq_root;
    return 0;
}
```

输出:

```cpp
10000 10
```

*   [**动态内存分配**](https://www.geeksforgeeks.org/dynamic-memory-allocation-in-c-using-malloc-calloc-free-and-realloc/) :我们可以使用指针动态分配内存。动态分配内存的好处是，在我们显式删除它之前，它不会被删除。

## C

```cpp
// C program to dynamically allocate an
// array of given size.

#include <stdio.h>
#include <stdlib.h>
int* createArr(int n)
{
    int* arr = (int*)(malloc(n * sizeof(int)));
    return arr;
}

int main()
{
    int* pt = createArr(10);
    return 0;
}
```

## C++

```cpp
// C++ program to dynamically allocate an
// array of given size.
#include <iostream>
using namespace std;

int* createArr(int n)
{
    return new int[n];
}

int main()
{
    int* pt = createArr(10);
    return 0;
}
```

*   **实现数据结构。**
    例[链表](https://www.geeksforgeeks.org/data-structures/linked-list/)[树](https://www.geeksforgeeks.org/binary-tree-data-structure/)等。我们不能使用 [C++ 引用](https://www.geeksforgeeks.org/references-in-c/)来实现这些数据结构，因为引用固定在一个位置(例如，我们不能使用引用遍历链表)
*   **在内存地址有用的地方进行系统级编程**。例如多线程使用的共享内存。更多示例参见[通过共享内存](https://www.geeksforgeeks.org/ipc-shared-memory/)、[C/c++ ](https://www.geeksforgeeks.org/socket-programming-in-cc-handling-multiple-clients-on-server-without-multi-threading/)中的 Socket 编程等