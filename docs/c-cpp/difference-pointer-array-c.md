# C 语言中指针和数组的区别？

> 原文:[https://www.geeksforgeeks.org/difference-pointer-array-c/](https://www.geeksforgeeks.org/difference-pointer-array-c/)

指针用于存储动态分配数组的地址，以及作为参数传递给函数的数组。在其他上下文中，数组和指针是两回事，请参见下面的程序来证明这一说法。
*大小运算符的行为*

## C++

```cpp
// 1st program to show that array and pointers are different
#include <iostream>
using namespace std;

int main()
{
    int arr[] = { 10, 20, 30, 40, 50, 60 };
    int* ptr = arr;

    // sizof(int) * (number of element in arr[]) is printed
    cout << "Size of arr[] " << sizeof(arr) << "\n";

    // sizeof a pointer is printed which is same for all
    // type of pointers (char *, void *, etc)
    cout << "Size of ptr " << sizeof(ptr);
    return 0;
}
```

## C

```cpp
// 1st program to show that array and pointers are different
#include <stdio.h>

int main()
{
    int arr[] = { 10, 20, 30, 40, 50, 60 };
    int* ptr = arr;

    // sizof(int) * (number of element in arr[]) is printed
    printf("Size of arr[] %ld\n", sizeof(arr));

    // sizeof a pointer is printed which is same for all
    // type of pointers (char *, void *, etc)
    printf("Size of ptr %ld", sizeof(ptr));
    return 0;
}
```

**Output**

```cpp
Size of arr[] 24
Size of ptr 8
```

*不允许给数组变量分配任何地址。*

## C++

```cpp
// IInd program to show that array
// and pointers are different
#include <iostream>
using namespace std;

int main()
{
   int arr[] = {10, 20}, x = 10;
   int *ptr = &x; // This is fine
   arr = &x;  // Compiler Error
   return 0;
}

// This code is contributed by Shubhamsingh10
```

## C

```cpp
// IInd program to show that array and pointers are different
#include <stdio.h>

int main()
{
   int arr[] = {10, 20}, x = 10;
   int *ptr = &x; // This is fine
   arr = &x;  // Compiler Error
   return 0;
}
```

**输出:**

```cpp
 Compiler Error: incompatible types when assigning to 
              type 'int[2]' from type 'int *' 
```

更多不同见[上一篇关于这个话题的帖子](https://www.geeksforgeeks.org/g-fact-5/)。
***虽然数组和指针是不同的东西，但数组的以下属性使它们看起来相似。***

1.  *数组名称给出数组第一个元素的地址。*

以下面的程序为例。

## C++

```cpp
// 1st program to show that array and pointers are different
#include <iostream>
using namespace std;
int main()
{
    int arr[] = { 10, 20, 30, 40, 50, 60 };

    // Assigns address of array to ptr
    int* ptr = arr;
    cout << "Value of first element is " << *ptr;
    return 0;
}
```

## C

```cpp
#include <stdio.h>
int main()
{
    int arr[] = { 10, 20, 30, 40, 50, 60 };
    // Assigns address of array to ptr
    int* ptr = arr;
    printf("Value of first element is %d", *ptr);
    return 0;
}
```

**Output**

```cpp
Value of first element is 10
```

*使用指针算法访问数组成员。*
编译器使用指针算法访问数组元素。例如，像“arr[i]”这样的表达式被编译器视为*(arr + i)。这就是为什么像*(arr + i)这样的表达式适用于数组 arr，而像 ptr[i]这样的表达式也适用于指针 ptr。

## C++

```cpp
#include <iostream>
using namespace std;

int main()
{
    int arr[] = { 10, 20, 30, 40, 50, 60 };
    int* ptr = arr;
    cout << "arr[2] = " << arr[2] << "\n";
    cout << "*(arr + 2) = " << *(arr + 2) << "\n";
    cout << "ptr[2] = " << ptr[2] << "\n";
    cout << "*(ptr + 2) = " << *(ptr + 2) << "\n";
    return 0;
}
```

## C

```cpp
#include <stdio.h>

int main()
{
   int arr[] = {10, 20, 30, 40, 50, 60};
   int *ptr = arr;
   printf("arr[2] = %d\n", arr[2]);
   printf("*(arr + 2) = %d\n", *(arr + 2));
   printf("ptr[2] = %d\n", ptr[2]);
   printf("*(ptr + 2) = %d\n", *(ptr + 2));
   return 0;
}
```

**Output**

```cpp
arr[2] = 30
*(arr + 2) = 30
ptr[2] = 30
*(ptr + 2) = 30
```

*数组参数总是作为指针传递，即使我们使用了方括号。*

## C++

```cpp
#include <bits/stdc++.h>
using namespace std;

int fun(int ptr[])
{
    int x = 10;

    // Size of a pointer is printed
    cout << "sizeof(ptr) = "
         << (int)sizeof(*ptr)
         << endl;

    // This allowed because ptr is a
    // pointer, not array
    ptr = &x;

    cout <<"*ptr =  " << *ptr;

    return 0;
}

// Driver code
int main()
{
    int arr[] = { 10, 20, 30, 40, 50, 60 };

    // Size of a array is printed
    cout << "sizeof(arr) = "
         << (int)sizeof(arr)
         << endl;

    fun(arr);

    return 0;
}

// This code is contributed by shivanisinghss2110
```

## C

```cpp
#include <stdio.h>

int fun(int ptr[])
{
    int x = 10;

    // size of a pointer is printed
    printf("sizeof(ptr) = %d\n", (int)sizeof(*ptr));

    // This allowed because ptr is a pointer, not array
    ptr = &x;

    printf("*ptr = %d ", *ptr);

    return 0;
}

// Driver code
int main()
{
    int arr[] = { 10, 20, 30, 40, 50, 60 };

    // size of a array is printed
    printf("sizeof(arr) = %d\n", (int)sizeof(arr));
    fun(arr);
    return 0;
}
```

**Output**

```cpp
sizeof(arr) = 24
sizeof(ptr) = 4
*ptr = 10 
```

详见[C](https://www.geeksforgeeks.org/g-fact-5/)中指针对数组。

本文由**阿沛·拉提**供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论