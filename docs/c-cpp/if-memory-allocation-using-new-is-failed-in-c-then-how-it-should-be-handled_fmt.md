# 如果使用 `new` 的内存分配在 C++ 中失败，那么应该如何处理？

> 原文: [https://www.geeksforgeeks.org/if-memory-allocation-using-new-is-failed-in-c-then-how-it-should-be-handled/](https://www.geeksforgeeks.org/if-memory-allocation-using-new-is-failed-in-c-then-how-it-should-be-handled/)

在本文中，如果使用 [`new`](https://www.geeksforgeeks.org/new-and-delete-operators-in-cpp-for-dynamic-memory/) 的[内存分配](https://www.geeksforgeeks.org/dynamic-memory-allocation-in-c-using-malloc-calloc-free-and-realloc/)在 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 中失败，那么应该如何处理？当使用 `new` 运算符动态创建类的[对象时](https://www.geeksforgeeks.org/c-classes-and-objects/)，该对象会占用堆中的内存。以下是必须记住的主要事情:

*   如果[堆内存](https://www.geeksforgeeks.org/stack-vs-heap-memory-allocation/)中没有足够的内存怎么办？我应该怎么做？
*   如果内存没有分配成功，如何避免项目崩溃？

下面是占用大量内存的程序，这样问题就会出现。在[try-catch块](https://www.geeksforgeeks.org/exception-handling-c/)中使用内存分配语句，用于[防止内存崩溃](https://www.geeksforgeeks.org/what-is-memory-leak-how-can-we-avoid/)，当内存分配失败时会抛出异常。

**程序 1:**

## C++

```cpp
// C++ program to illustrate memory
// failure when very large memory
// is allocated
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Allocate huge amount of memory
    long MEMORY_SIZE = 0x7fffffff;

    // Put memory allocation statement
    // in the try catch block
    try {
        char* ptr = new char[MEMORY_SIZE];

        // When memory allocation fails,
        // below line is not be executed
        // & control will go in catch block
        cout << "Memory is allocated"
             << " Successfully" << endl;
    }

    // Catch Block handle error
    catch (const bad_alloc& e) {

        cout << "Memory Allocation"
             << " is failed: "
             << e.what()
             << endl;
    }

    return 0;
}
```

**输出:**

```cpp
Memory Allocation is failed: std::bad_alloc
```