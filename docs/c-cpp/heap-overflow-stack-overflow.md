# 堆溢出和栈溢出

> 原文:[https://www.geeksforgeeks.org/heap-overflow-stack-overflow/](https://www.geeksforgeeks.org/heap-overflow-stack-overflow/)

**堆溢出:**

堆是[进程内存](https://www.geeksforgeeks.org/memory-layout-of-c-program/)的一个区域，用于存储动态变量。这些变量使用 malloc()和 calloc()函数分配，使用 realloc()函数调整大小，它们是 c 的内置函数。这些变量可以全局访问，一旦我们在堆上分配内存，我们就有责任在使用后释放内存空间。有两种情况会导致堆溢出:

1.  If we allocate memory continuously and don't release the memory space after use, it may lead to memory leakage-memory is still in use, but it can't be used by other processes.

    ```cpp
    // C program to demonstrate heap overflow
    // by continuously allocating memory
    #include<stdio.h>

    int main()
    {
        for (int i=0; i<10000000; i++)
        {
           // Allocating memory without freeing it
           int *ptr = (int *)malloc(sizeof(int));
        }
    }
    ```

2.  If we dynamically allocate a large number of variables.

    ```cpp
    // C program to demonstrate heap overflow
    // by allocating large memory
    #include<stdio.h>

    int main()
    {
        int *ptr = (int *)malloc(sizeof(int)*10000000));
    }
    ```

**堆栈溢出:**

堆栈是我们的[进程内存](https://www.geeksforgeeks.org/memory-layout-of-c-program/)的一个特殊区域，用于存储函数内部使用的局部变量、通过函数传递的参数及其返回地址。每当声明一个新的局部变量时，它就会被推送到堆栈上。在函数完成运行后，与函数相关联的所有变量都会被删除，它们使用的内存也会被释放。用户不需要手动释放堆栈空间。堆栈是后进先出的数据结构。

在我们计算机的内存中，堆栈大小是有限的。如果一个程序使用的内存空间超过了堆栈大小，那么堆栈溢出就会发生，并可能导致程序崩溃。有两种情况会发生栈溢出:

1.  If we declare a large number of local variables or declare an array or matrix or any large-sized high-dimensional array, it will lead to stack overflow.

    ```cpp
    // C program to demonstrate stack overflow
    // by allocating a large local memory
    #include<stdio.h>

    int main() {

       // Creating a matrix of size 10^5 x 10^5
       // which may result in stack overflow.
       int mat[100000][100000];
    }
    ```

2.  If the function recursively calls itself an infinite number of times, the stack cannot store a large number of local variables used in each function call, which will lead to stack overflow.

    ```cpp
    // C program to demonstrate stack overflow
    // by creating a non-terminating recursive
    // function.
    #include<stdio.h>

    void fun(int x)
    {
        if (x == 1)
           return;
        x = 6;
        fun(x);
    }

    int main()
    {
       int x = 5;
       fun(x);
    }
    ```

详见[C 程序内存布局](https://www.geeksforgeeks.org/memory-layout-of-c-program/)。