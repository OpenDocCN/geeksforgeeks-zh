# C 语言中的指针算法示例

> 原文:[https://www . geeksforgeeks . org/pointer-arithmetics-in-c-with-examples/](https://www.geeksforgeeks.org/pointer-arithmetics-in-c-with-examples/)

[指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)变量也被称为**地址数据类型**，因为它们用于存储另一个变量的地址。地址是分配给变量的内存位置。它不存储任何值。

因此，在 C 语言的中，只允许对[指针执行一些操作。这些运算与我们通常用于数学计算的运算略有不同。这些操作是:](https://www.geeksforgeeks.org/pointers-c-examples/)

1.  指针的递增/递减
2.  向指针添加整数
3.  指针的整数减法
4.  减去两个相同类型的指针

**<u>指针的递增/递减</u>**

**增量:**这是一个也属于加法的条件。当指针递增时，它实际上递增的数字等于它作为指针的数据类型的大小。

**例如:**
如果存储**地址 1000** 的整数指针递增，那么它将递增 2( **大小为 int** )并且它将指向的新地址为 **1002** 。而如果浮点型指针递增，那么它将递增 4(浮点的**大小)，并且新地址将是 **1004** 。
**减量:**也是减法下的一个条件。当指针递减时，它实际上递减的数量等于它作为指针的数据类型的大小。**

**例如:**
如果存储**地址 1000** 的整数指针递减，那么它将递减 2( **大小为 int** )并且它将指向的新地址为 **998** 。而如果浮点型指针递减，那么它将递减 4(浮点的**大小)，并且新地址将是 **996** 。**

下面是说明指针递增/递减的程序:

## C

```cpp
// C program to illustrate
// pointer increment/decrement

#include <stdio.h>

// Driver Code
int main()
{
    // Integer variable
    int N = 4;

    // Pointer to an integer
    int *ptr1, *ptr2;

    // Pointer stores
    // the address of N
    ptr1 = &N;
    ptr2 = &N;

    printf("Pointer ptr1 "
           "before Increment: ");
    printf("%p \n", ptr1);

    // Incrementing pointer ptr1;
    ptr1++ ;

    printf("Pointer ptr1 after"
           " Increment: ");
    printf("%p \n\n", ptr1);

    printf("Pointer ptr1 before"
           " Decrement: ");
    printf("%p \n", ptr1);

    // Decrementing pointer ptr1;
    ptr1--;

    printf("Pointer ptr1 after"
           " Decrement: ");
    printf("%p \n\n", ptr1);

    return 0;
}
```

**Output:** 

```cpp
Pointer ptr1 before Increment: 0x7ffcb19385e4 
Pointer ptr1 after Increment: 0x7ffcb19385e8 

Pointer ptr1 before Decrement: 0x7ffcb19385e8 
Pointer ptr1 after Decrement: 0x7ffcb19385e4
```

**<u>加法</u>**

当指针加上一个值时，该值首先乘以数据类型的大小，然后加到指针上。

## C

```cpp
// C program to illustrate pointer Addition
#include <stdio.h>

// Driver Code
int main()
{
    // Integer variable
    int N = 4;

    // Pointer to an integer
    int *ptr1, *ptr2;

    // Pointer stores the address of N
    ptr1 = &N;
    ptr2 = &N;

    printf("Pointer ptr2 before Addition: ");
    printf("%p \n", ptr2);

    // Addition of 3 to ptr2
    ptr2 = ptr2 + 3;
    printf("Pointer ptr2 after Addition: ");
    printf("%p \n", ptr2);

    return 0;
}
```

**Output:** 

```cpp
Pointer ptr2 before Addition: 0x7fffffdcd984 
Pointer ptr2 after Addition: 0x7fffffdcd990
```

**<u>减法</u>**

当指针减去一个值时，该值首先乘以数据类型的大小，然后从指针中减去。

下面是演示指针减法的程序:

## C

```cpp
// C program to illustrate pointer Subtraction
#include <stdio.h>

// Driver Code
int main()
{
    // Integer variable
    int N = 4;

    // Pointer to an integer
    int *ptr1, *ptr2;

    // Pointer stores the address of N
    ptr1 = &N;
    ptr2 = &N;

    printf("Pointer ptr2 before Subtraction: ");
    printf("%p \n", ptr2);

    // Subtraction of 3 to ptr2
    ptr2 = ptr2 - 3;
    printf("Pointer ptr2 after Subtraction: ");
    printf("%p \n", ptr2);

    return 0;
}
```

**Output:** 

```cpp
Pointer ptr2 before Subtraction: 0x7ffcf1221b24 
Pointer ptr2 after Subtraction: 0x7ffcf1221b18
```

**<u>两个指针的相减</u>**

只有当两个指针具有相同的数据类型时，才有可能相减。结果是通过计算两个指针的地址之差并根据指针数据类型计算它是多少位数据而产生的。两个指针的相减得到两个指针之间的增量。

**例如:**
两个整数指针表示 **ptr1(地址:1000)** 和 **ptr2(地址:1016)** 相减。地址相差 16 个字节。由于 int 的大小为 2 字节，因此 ptr1 和 ptr2 之间的**增量由 **(16/2) = 8** 给出。**

下面是说明两个指针相减的实现:

## C

```cpp
// C program to illustrate Subtraction
// of two pointers
#include <stdio.h>

// Driver Code
int main()
{
    int x;

    // Integer variable
    int N = 4;

    // Pointer to an integer
    int *ptr1, *ptr2;

    // Pointer stores the address of N
    ptr1 = &N;
    ptr2 = &N;

    // Incrementing ptr2 by 3
    ptr2 = ptr2 + 3;

    // Subtraction of ptr2 and ptr1
    x = ptr2 - ptr1;

    // Print x to get the Increment
    // between ptr1 and ptr2
    printf("Subtraction of ptr1 "
           "& ptr2 is %d\n",
           x);

    return 0;
}
```

**Output:** 

```cpp
Subtraction of ptr1 & ptr2 is 3
```

**数组上的指针算法:**
指针包含地址。添加两个地址没有意义，因为不知道它会指向什么。减去两个地址可以计算两个地址之间的偏移量。数组名的作用类似于指针常量。这个指针常量的值是第一个元素的地址。**例如:**如果一个数组名为 arr，那么 arr 和& arr[0]可以用来引用数组作为指针。

下面是演示数组指针算法的程序:

**程序 1:**

## C

```cpp
// C program to illustrate the array
// traversal using pointers
#include <stdio.h>

// Driver Code
int main()
{

    int N = 5;

    // An array
    int arr[] = { 1, 2, 3, 4, 5 };

    // Declare pointer variable
    int* ptr;

    // Point the pointer to first
    // element in array arr[]
    ptr = arr;

    // Traverse array using ptr
    for (int i = 0; i < N; i++) {

        // Print element at which
        // ptr points
        printf("%d ", ptr[0]);
        ptr++ ;
    }
}
```

**Output:** 

```cpp
1 2 3 4 5
```

**程序 2:**

## C

```cpp
// C program to illustrate the array
// traversal using pointers in 2D array
#include <stdio.h>

// Function to traverse 2D array
// using pointers
void traverseArr(int* arr,
                 int N, int M)
{

    int i, j;

    // Traverse rows of 2D matrix
    for (i = 0; i < N; i++) {

        // Traverse columns of 2D matrix
        for (j = 0; j < M; j++) {

            // Print the element
            printf("%d ", *((arr + i * M) + j));
        }
        printf("\n");
    }
}

// Driver Code
int main()
{

    int N = 3, M = 2;

    // A 2D array
    int arr[][2] = { { 1, 2 },
                     { 3, 4 },
                     { 5, 6 } };

    // Function Call
    traverseArr((int*)arr, N, M);
    return 0;
}
```

**Output:** 

```cpp
1 2 
3 4 
5 6
```