# C/C++中sizeof(int*)和sizeof(int)的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-sizeofint-and-sizeofint-in-c-c/](https://www.geeksforgeeks.org/difference-between-sizeofint-and-sizeofint-in-c-c/)

`sizeof()`是[C](https://www.geeksforgeeks.org/c/)或[C++](https://www.geeksforgeeks.org/c-plus-plus/)中常用的运算符。它是一个编译时[一元运算符](https://www.geeksforgeeks.org/unary-operators-cc/)，可用于计算其操作数的大小。`sizeof()`的结果为无符号整型，通常用`size_t`表示。该运算符可应用于任何数据类型，包括[基元类型](https://www.geeksforgeeks.org/uninitialized-primitive-data-types-in-c-c/)如整数和浮点类型、指针类型，或复合数据类型如[结构](https://www.geeksforgeeks.org/structures-c/)、[联合](https://www.geeksforgeeks.org/union-c/)等。

> `int`表示数据类型为整数的变量。
> `sizeof(int)`返回用于存储整数的字节数。
> `int*`表示指向数据类型为整数的变量的指针。
> `sizeof(int*)`返回用于存储指针的字节数。

因为运算符的大小返回数据类型或我们传递给它的参数的大小。因此，在将变量(`int*`)传递给它之后，它应该返回的值是:
*   由于`int*`指向一个地址位置，因为它是指向一个变量的指针，所以，`sizeof(int*)`只是暗示机器上内存位置的值，内存位置本身是4字节到8字节的整数值。
*   在32位机器上，`sizeof(int*)`将返回值4，因为32位机器上内存位置的地址值是4字节整数。
*   类似地，在64位机器上，它将返回一个值8，因为在64位机器上，内存位置的地址是8字节整数。

现在，向它传递变量(`int`)后它应该返回的值:
*   由于整数类型变量中的`int`。因此，`sizeof(int)`简单地表示一个整数的大小值。
*   无论是32位机器还是64位机器，`sizeof(int)`将始终返回一个值4作为整数的大小。

下图为64位机器上操作员的尺寸:

## C

```cpp
// C program to illustrate the
// sizeof operator
#include <stdio.h>

// Driver code
int main()
{
    // Print the sizeof integer
    printf("Size of (int) = %lu"
           " bytes\n",
           sizeof(int));

// Print the size of (int*)
    printf("Size of (int*) = %lu"
           " bytes\n",
           sizeof(int*));

return 0;
}
```

## C++

```cpp
// C program to illustrate the
// sizeof operator
#include "bits/stdc++.h"
using namespace std;

// Driver Code
int main()
{
    // Print the sizeof integer
    cout << "Size of (int) = "
         << sizeof(int) << " bytes\n";

// Print the size of (int*)
    cout << "Size of (int *) = "
         << sizeof(int*) << " bytes\n";

return 0;
}
```

**Output:**

```cpp
Size of (int) = 4 bytes
Size of (int*) = 8 bytes
```