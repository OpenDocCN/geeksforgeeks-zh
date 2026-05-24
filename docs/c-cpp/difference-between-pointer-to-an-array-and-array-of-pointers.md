# 指向数组的指针和指针数组的区别

> 原文:[https://www . geesforgeks . org/指针指向数组和指针数组的区别/](https://www.geeksforgeeks.org/difference-between-pointer-to-an-array-and-array-of-pointers/)

<u>**[指针指向一个数组](https://www.geeksforgeeks.org/pointer-array-array-pointer/)** :</u>

[指向一个数组的指针](https://www.geeksforgeeks.org/pointer-array-array-pointer/)也称为[数组指针](https://www.geeksforgeeks.org/pointer-array-array-pointer/)。我们使用指针来访问数组的组件。

```cpp
  int a[3] = {3, 4, 5 }; 
  int *ptr = a; 

```

我们有一个指针 ptr，它指向数组的第 0 个部分。我们同样可以声明一个指针，它可以指向整个数组，而不仅仅是数组的一个组件。
**语法**:

```cpp
data type (*var name)[size of array];
```

数组指针的声明:

```cpp
// pointer to an array of five numbers
 int (* ptr)[5] = NULL;     
```

上面的声明是指向五个整数的数组的指针。我们用括号来表示指向数组的指针。由于下标的优先级高于间接寻址，因此将间接寻址操作符和指针名称封装在括号内至关重要。

**示例:**

```cpp
// C program to demonstrate
// pointer to an array.

#include <stdio.h>

int main()
{

    // Pointer to an array of five numbers
    int(*a)[5];

    int b[5] = { 1, 2, 3, 4, 5 };

    int i = 0;

    // Points to the whole array b

    a = &b;

    for (i = 0; i < 5; i++)

        printf("%d\n", *(*a + i));

    return 0;
}
```

**Output:**

```cpp
1
2
3
4
5

```

<u>**[指针阵列](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)** :</u>

“[指针数组](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)是一个[指针变量](https://www.geeksforgeeks.org/pointers-c-examples/)的数组。它也被称为指针数组。
**语法**:

```cpp
int *var_name[array_size];
```

指针数组的声明:

```cpp
 int *ptr[3];
```

我们可以创建单独的指针变量，它可以指向不同的值，或者我们可以创建一个指针的整数数组，它可以指向所有的值。

**示例:**

```cpp
// C program to demonstrate
// example of array of pointers.

#include <stdio.h>

const int SIZE = 3;

void main()
{

    // creating an array
    int arr[] = { 1, 2, 3 };

    // we can make an integer pointer array to
    // storing the address of array elements
    int i, *ptr[SIZE];

    for (i = 0; i < SIZE; i++) {

        // assigning the address of integer.
        ptr[i] = &arr[i];
    }

    // printing values using pointer
    for (i = 0; i < SIZE; i++) {

        printf("Value of arr[%d] = %d\n", i, *ptr[i]);
    }
}
```

**Output:**

```cpp
Value of arr[0] = 1
Value of arr[1] = 2
Value of arr[2] = 3

```

**示例:**我们同样可以制作一个指向字符的指针数组来存储字符串列表。

```cpp
#include <stdio.h>

const int size = 4;

void main()
{

    // array of pointers to a character
    // to store a list of strings
    char* names[] = {
        "amit",
        "amar",
        "ankit",
        "akhil"
    };

    int i = 0;

    for (i = 0; i < size; i++) {
        printf("%s\n", names[i]);
    }
}
```

**Output:**

```cpp
amit
amar
ankit
akhil

```