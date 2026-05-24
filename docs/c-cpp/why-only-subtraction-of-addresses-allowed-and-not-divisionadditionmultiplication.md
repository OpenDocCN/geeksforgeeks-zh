# 为什么只允许减地址不允许除/加/乘

> 原文:[https://www . geesforgeks . org/why-only-减法-地址-允许和不允许-除法-加法-乘法/](https://www.geeksforgeeks.org/why-only-subtraction-of-addresses-allowed-and-not-divisionadditionmultiplication/)

**为什么允许减法？**可以减去两个地址，因为两个地址之间的内存将是有效内存。
让我们假设内存 Ptr_1 和 ptr_2 有效地址。很明显，这两个地址之间的内存是有效的。
指针 ptr_1 指向 0x1cb0010 内存位置，指针 ptr_2 指向 0x1cb0030 内存位置。如果我们从 ptr_2 中减去 ptr_1，那么内存区域将位于这两个位置之间，这显然是一个有效的内存位置。

## C++

```cpp
// C++ program to demonstrate that pointer
// subtraction is allowed.
#include <iostream>
using namespace std;

int main()
{
    int* ptr_1 = (int*)malloc(sizeof(int));
    int* ptr_2 = (int*)malloc(sizeof(int));
    cout << "ptr_1:" << ptr_1 <<  " ptr_2: "<< ptr_2 << endl;
    cout << "Difference: "<< ptr_2 - ptr_1;
    free(ptr_1);
    free(ptr_2);
    return 0;
}

// This code is contributed by shivanisinghss2110.
```

## C

```cpp
// C program to demonstrate that pointer
// subtraction is allowed.
#include <stdio.h>
#include <stdlib.h>
int main()
{
    int* ptr_1 = (int*)malloc(sizeof(int));
    int* ptr_2 = (int*)malloc(sizeof(int));
    printf("ptr_1: %p  ptr_2: %p\n", ptr_1, ptr_2);
    printf("Difference: %lu", ptr_2 - ptr_1);
    free(ptr_1);
    free(ptr_2);
    return 0;
}
```

```cpp
Output:
ptr_1: 0x1cb0010 ptr_2: 0x1cb0030
Difference: 8
```

**为什么不允许加、乘、除或模？？**
如果我们对 ptr_1 和 ptr_2 执行加法、乘法、除法或模运算，那么结果地址可能是也可能不是有效地址。可能超出范围或地址无效。这就是编译器不允许在有效地址上进行这些操作的原因。

## C++

```cpp
// C++ program to demonstrate addition / division
// / multiplication not allowed on pointers.
#include <iostream>
#include <bits/stdc++.h>
using namespace std;
int main()
{
    int* ptr_1 = (int*)malloc(sizeof(int));
    int* ptr_2 = (int*)malloc(sizeof(int));
    cout <<"addition:%lu multipicaion:%lu division:%lu\n"<<
           ptr_2 + ptr_1<< ptr_2 * ptr_1<< ptr_2 / ptr_1;
    free(ptr_1);
    free(ptr_2);
    return 0;
}

// This code is contributed by shivanisinghss2110
```

## C

```cpp
// C program to demonstrate addition / division
// / multiplication not allowed on pointers.
#include <stdio.h>
#include <stdlib.h>
int main()
{
    int* ptr_1 = (int*)malloc(sizeof(int));
    int* ptr_2 = (int*)malloc(sizeof(int));
    printf("addition:%lu multipicaion:%lu division:%lu\n",
           ptr_2 + ptr_1, ptr_2 * ptr_1, ptr_2 / ptr_1);
    free(ptr_1);
    free(ptr_2);
    return 0;
}
```

```cpp
Output: prog.c: In function 'main':
prog.c:8:60: error: invalid operands to 
binary + (have 'int *' and 'int *')
printf("addition:%lu multipicaion:%lu 
division:%lu\n", ptr_2+ptr_1, ptr_2*ptr_1,
ptr_2/ptr_1);
```