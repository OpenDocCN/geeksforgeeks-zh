# 如何在 C++ 中从函数返回局部变量

> 原文:[https://www . geesforgeks . org/如何从 c 中的函数返回局部变量/](https://www.geeksforgeeks.org/how-to-return-local-variables-from-a-function-in-c/)

下面的文章讨论了返回在[函数](https://www.geeksforgeeks.org/functions-in-c/)中创建的[局部变量](https://www.geeksforgeeks.org/scope-of-variables-in-c/https://www.geeksforgeeks.org/scope-of-variables-in-c/)的方法，这可以通过将[指针](https://www.geeksforgeeks.org/pointers-in-c-and-c-set-1-introduction-arithmetic-and-array/)从[调用函数](https://www.geeksforgeeks.org/what-happens-when-we-call-a-function/)返回到[调用函数](https://www.geeksforgeeks.org/parameter-passing-techniques-in-c-cpp/)来实现。

**当你像往常一样试图返回一个局部变量时会发生什么？**

例如，在下面的代码中，当在函数内部创建数组并返回给调用者函数时，它会抛出一个[运行时错误](https://www.geeksforgeeks.org/runtime-errors/)，因为数组是在[堆栈内存](https://www.geeksforgeeks.org/stack-vs-heap-memory-allocation/)中创建的，因此一旦函数结束，它就会被删除。

## C++

```cpp
#include <bits/stdc++.h>
using namespace std;

// Function to return an
// array
int* fun()
{
    int arr[5] = { 1, 2, 3, 4, 5 };
    return arr;
}
// Driver Code
int main()
{

    int* arr = fun();
    // Will cause error
    cout << arr[2];

    return 0;
}
```

**输出**

```cpp
Segmentation Fault (SIGSEGV)
```

**如何从函数返回局部变量？**

但是有一种方法可以使用指针访问函数的局部变量，方法是创建另一个指向要返回的变量的指针变量，并返回指针变量本身。

*   **返回局部变量:**

## C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to return
// a pointer
int* fun()
{
    int x = 20;
    int* ptr = &x;
    return ptr;
}
// Driver Code
int main()
{

    int* arr = fun();
    cout << *arr;
    return 0;
}
```

**Output**

```cpp
20
```

*   **返回数组:**

## C++

```cpp
#include <bits/stdc++.h>
using namespace std;

// Function to return an
// array
int* fun()
{
    int arr[5] = { 1, 2, 3, 4, 5 };
    int *ptr = arr;
    return ptr;
}
// Driver Code
int main()
{

    int* arr = fun();
    cout << arr[2];

    return 0;
}
```

**Output**

```cpp
3
```