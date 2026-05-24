# C 中 Malloc 的替代物

> 原文:[https://www.geeksforgeeks.org/alternative-of-malloc-in-c/](https://www.geeksforgeeks.org/alternative-of-malloc-in-c/)

C 或 C++ 中的[数组](https://www.geeksforgeeks.org/introduction-to-arrays/)是存储在连续内存位置的项目集合，可以使用数组的索引随机访问元素。它们用于存储类似类型的元素，因为所有元素的数据类型必须相同。它们可以用来存储原始数据类型的集合，例如任何特定类型的 int、float、double、char 等。此外， [C](https://www.geeksforgeeks.org/c-programming-language/) 或 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中的数组可以存储派生的数据类型，如结构、指针等。下面给出了一个数组的生动的表示。

![array](img/13b7429b646a58c1b6e67867ce0dab9c.png)

C++ 中有两种类型的数组/字符串声明，如下所示

1.  静态声明
2.  动态声明

**方式一:**静态申报

**方法:**静态声明可以通过 3 种方式完成

*   通过指定大小进行数组声明
*   通过初始化元素进行数组声明
*   通过指定大小和初始化元素来声明数组

**通过指定大小进行数组声明**

**语法:**

```cpp
int arr1[10];
// Array declaration by specifying size
```

```cpp
int n = 10;
int arr2[n];
```

> **注**:用最近的 C/C++ 版本，我们也可以声明一个用户指定大小的数组

**通过初始化元素进行数组声明**

```cpp
int arr[] = {10, 20, 30, 40};
// Array declaration by initializing elements
```

> 编译器创建大小为 4 的数组。这与“int arr[4] = {10，20，30，40}”相同

**通过指定大小和初始化元素进行数组声明**

**语法:**

```cpp
int arr[6] = {10, 20, 30, 40} ;
// Array declaration by specifying size
// and initializing elements
```

> 编译器创建一个大小为 6 的数组，初始化用户指定的前 4 个元素，其余两个元素如上，如下所示:
> 
> ```cpp
> int arr[] = {10, 20, 30, 40, 0, 0}"
> ```

> **注意:**在静态声明中，内存将在[堆栈内存](https://www.geeksforgeeks.org/stack-vs-heap-memory-allocation/)T4 中分配。

**实现:**下面是演示静态声明的 C 程序

**例 1:**

## C

```cpp
// C Program to Implement Static Declaration

// Importing standard input output operations file
#include <stdio.h>

// Main driver method
int main()
{
  // Static declaration of array so it
  // will get memory in Stack memory
  int first_array[2];

  // Assign value 10
  first_array[0] = 10;

  // Assign value 20
  first_array[1] = 20;

  // Printing value
  printf("%d %d", first_array[0],
                  first_array[1]);
  return 0;
}
```

**Output**

```cpp
10 20
```

**动态声明:** Malloc 用于动态分配数组。在这种情况下，内存将在**堆**中分配。程序完成后，分配的内存将被释放。

**例 2:**

## C

```cpp
// C program to implement Dynamic Memory Allocation
// using Malloc

// Importing standard input output files
#include<stdio.h>
// Include this library for malloc
#include<stdlib.h>

// Main driver method
int main()
{
  // Memory will get allocated in  Heap and
  // RHS is implicitly typecasted to integer as
  // LHS is having integer as a return type
  int *first_array = (int*)malloc(sizeof(int)*2);

  // Creating and initializing array

  // Custom integer values on indicis as specified
  first_array[0] = 10;
  first_array[1] = 20;

  // Printing elements of both the arrays
  printf("%d %d", first_array[0],
                  first_array[1]);
  return 0;
}
```

**Output**

```cpp
10 20
```

现在我们来看一个古怪的目标，即找到一种替代方法来分配内存，而不是动态声明

**例 3:**

## C

```cpp
// C Program to implement Alternative to Malloc

// Importing standard input output file
#include<stdio.h>

// Main driver method
int main()
{
  // Alternative of Malloc '*' operator refers
  // to address of array memory block
  int *first_array = (int[2]){};

  // Creating and initializing array together

  // Custom input element at array indicies
  first_array[0] = 10;
  first_array[1] = 20;

  // Printing the array indicies as passed in argument
  printf("%d %d", first_array[0],
                  first_array[1]);
  return 0;
}
```

**Output**

```cpp
10 20
```