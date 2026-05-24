# std::multiplies in C++

> 原文: [https://www.geeksforgeeks.org/stdmultiplies-in-cpp/](https://www.geeksforgeeks.org/stdmultiplies-in-cpp/)

用于执行乘法的函数对象。在两个类型为 `T` 的实例上有效调用 `operator*`。

**语法:**

```cpp
template <class T> struct multiplies : binary_function <T,T,T>
{
    T operator() (const T& x, const T& y) const {return x*y;}
};
```

**模板参数：**
- `T` - 参数和函数调用返回值的类型。该类型应支持 `operator*` 操作。

**成员类型：**
- `x`：成员 `operator()` 中第一个参数的类型。
- `y`：成员 `operator()` 中第二个参数的类型。
- `result_type`：成员 `operator()` 返回的类型。

**例:**

```cpp
// C++ program to illustrate std::multiplies
// by multiplying the respective elements of 2 arrays
#include <iostream> // std::cout
#include <functional> // std::multiplies
#include <algorithm> // std::transform

int main()
{
    // First array
    int first[] = { 1, 2, 3, 4, 5 };

    // Second array
    int second[] = { 10, 20, 30, 40, 50 };

    // Result array
    int results[5];

    // std::transform applies std::multiplies to the whole array
    std::transform(first, first + 5, second, results, std::multiplies<int>());

    // Printing the result array
    for (int i = 0; i < 5; i++)
        std::cout << results[i] << " ";

    return 0;
}
```

**输出:**

```cpp
10 40 90 160 250
```

**另一个例子:**

```cpp
// C++ program to illustrate std::multiplies
// by multiplying all array elements with a number
#include <bits/stdc++.h>

int main()
{
    // Array with elements to be multiplying
    int arr[] = { 10, 20, 30 };

    // size of array
    int size = sizeof(arr) / sizeof(arr[0]);

    // Variable with which array is to be multiplied
    int num = 10;

    // Variable to store result
    int result;

    // using std::accumulate to perform multiplication on array with num
    // using std::multiplies
    result = std::accumulate(arr, arr + size, num, std::multiplies<int>());

    // Printing the result
    std::cout << "The result of 10 * 10 * 20 * 30 is " << result;

    return 0;
}
```

**输出:**

```cpp

```

本文由 **Rohit Thapliyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。