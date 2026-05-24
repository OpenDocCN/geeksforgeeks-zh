# 标准::c++ 中的加号

> 原文:[https://www.geeksforgeeks.org/stdplus-in-c/](https://www.geeksforgeeks.org/stdplus-in-c/)

它是用于执行加法的函数对象。其调用返回其两个参数相加结果的对象类(由运算符+返回)。

**语法:**

```cpp
template  struct plus : binary_function  
{
  T operator() (const T& x, const T& y) const { return x + y; }
};

Template parameters :
T - Type of the arguments and return type of the functional call.
    The type shall support the operation (operator+).

Member types :
x : Type of the first argument in member operator()
y : Type of the second argument in member operator()
result_type : Type returned by member operator()

```

```cpp
// C++ program to illustrate std::plus
// by adding the respective elements of 2 arrays
#include <iostream> // std::cout
#include <functional> // std::plus
#include <algorithm> // std::transform

int main()
{
    // First array
    int first[] = { 1, 2, 3, 4, 5 };

    // Second array
    int second[] = { 10, 20, 30, 40, 50 };

    // Result array
    int results[5];

    // std::transform applies std::plus to the whole array
    std::transform(first, first + 5, second, results, std::plus<int>());

    // Printing the result array
    for (int i = 0; i < 5; i++)
        std::cout << results[i] << " ";

    return 0;
}
```

输出:

```cpp
11 22 33 44 55 

```

**另一个例子:**

```cpp
// C++ program to illustrate std::plus
// by adding all array elements with a number
#include <bits/stdc++.h>

int main()
{
    // Array with elements to be added
    int arr[] = { 10, 20, 30 };

    // size of array
    int size = sizeof(arr) / sizeof(arr[0]);

    // Variable with which array is to be added
    int num = 100;

    // Variable to store result
    int result;

    // using std::accumulate to perform addition on array with num
    // using std::plus
    result = std::accumulate(arr, arr + size, num, std::plus<int>());

    // Printing the result
    std::cout << "The result of 100 + 10 + 20 + 30 is " << result;

    return 0;
}
```

输出:

```cpp
The result of 100 + 10 + 20 + 30 is 160
```

本文由 **Rohit Thapliyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。