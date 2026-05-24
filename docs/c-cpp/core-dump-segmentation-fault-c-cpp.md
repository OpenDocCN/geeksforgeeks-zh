# C/c++ 中的核心转储(分段故障)

> 原文:[https://www . geesforgeks . org/core-dump-segmentation-fault-c-CPP/](https://www.geeksforgeeks.org/core-dump-segmentation-fault-c-cpp/)

核心转储/分段故障是由访问“不属于您的”内存引起的一种特定错误

*   当一段代码试图在内存中的只读位置或释放的内存块中执行读写操作时，称为核心转储。
*   这是一个指示内存损坏的错误。

**常见分段故障场景:**

*   **修改字符串文字:**
    下面的程序可能会崩溃(给出分段错误)，因为行*(str+1) = 'n '试图写入只读存储器。

## C

```cpp
int main()
{
   char *str;

   /* Stored in read only part of data segment */
   str = "GfG";    

   /* Problem:  trying to modify read only memory */
   *(str+1) = 'n';
   return 0;
}
```

```cpp
Abnormal termination of program.
```

详见[C](https://www.geeksforgeeks.org/storage-for-strings-in-c/)中字符串的存储

*   **访问被释放的地址:**
    在下面的代码中，指针 p 在释放内存块后被取消引用，这是编译器不允许的。因此在运行时会产生错误段错误或异常程序终止。
    示例:

## C++

```cpp
// C++ program to illustrate
// Core Dump/Segmentation fault
#include <iostream>
using namespace std;

int main(void)
{
    // allocating memory to p
    int* p = (int*) malloc(8*sizeof(int));

    *p = 100;

    // deallocated the space allocated to p
    free(p);

    // core dump/segmentation fault
    //  as now this statement is illegal
    *p = 110;

    return 0;
}

// This code is contributed by shivanisinghss2110
```

## C

```cpp
// C program to illustrate
// Core Dump/Segmentation fault
#include <stdio.h>
#include<alloc.h>
int main(void)
{
    // allocating memory to p
    int* p = malloc(8);
    *p = 100;

    // deallocated the space allocated to p
    free(p);

    // core dump/segmentation fault
    //  as now this statement is illegal
    *p = 110;

    return 0;
}
```

输出:

```cpp
Abnormal termination of program.
```

*   **超出数组索引界限访问:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate segmentation
// fault when array out of bound is accessed.
#include <iostream>
using namespace std;

int main()
{
   int arr[2];
   arr[3] = 10;  // Accessing out of bound
   return 0;
}
```

输出:

```cpp
Abnormal termination of program.
```

*   **scanf()使用不当:**
    scanf()函数需要一个变量的地址作为输入。在本程序中，n 取
    值 2，并假设其地址为 1000。如果我们将 n 传递给 scanf()，从 STDIN 获取的输入将被放置在无效内存 2 中，该内存应该是 1000。这是导致分段故障的内存损坏。

## C++

```cpp
// C++ program to demonstrate segmentation
// fault when value is passed to scanf
#include <iostream>
using namespace std;

int main()
{
   int n = 2;
   cout << " "<< n;
   return 0;
}

// This code is contributed by shivanisinghss2110
```

## C

```cpp
// C program to demonstrate segmentation
// fault when value is passed to scanf
#include <stdio.h>

int main()
{
   int n = 2;
   scanf(" ",n);
   return 0;
}
```

输出:

```cpp
Abnormal termination of program.
```

*   **堆栈溢出**
    这不是一个指针相关的问题，甚至代码可能没有单个指针。这是因为递归函数被反复调用，耗尽了所有的堆栈内存，导致堆栈溢出。堆栈内存不足也是一种内存损坏。它可以通过从递归函数返回一个基本条件来解决。

*   **取消引用未初始化的指针**
    在访问有效内存之前，指针必须指向有效内存。

## C++ 14

```cpp
// C++ program to demonstrate segmentation
// fault when uninitialized pointer is accessed.
#include <iostream>
using namespace std;

int main()
{
    int* p;
    cout << *p;
    return 0;
}
// This code is contributed by Mayank Tyagi
```

## C

```cpp
// C program to demonstrate segmentation
// fault when uninitialized pointer is accessed.
#include <stdio.h>

int main()
{
   int *p;
   printf("%d",*p);
   return 0;
}
```

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。