# STD::c++ 中的除法

> 原文:[https://www.geeksforgeeks.org/stddivides-in-cpp/](https://www.geeksforgeeks.org/stddivides-in-cpp/)

用于执行除法的函数对象。在两个类型为 T 的实例上有效调用**运算符/**

**语法:**

```cpp
 template  struct divides : binary_function  
{
    T operator() (const T& x, const T& y) const {return x/y;}
};

Template Parameters :
T - Type of the arguments and return type of the functional call.
    The type shall support the operation (operator /).

Member types :
x : Type of the first argument in member operator()
y : Type of the second argument in member operator()
result_type : Type returned by member operator()

```

**例:**

```cpp
// C++ program to illustrate std::divides
// by dividing the respective elements of 2 arrays
#include <iostream> // std::cout
#include <functional> // std::divides
#include <algorithm> // std::transform

int main()
{
    // First array
    int first[] = { 10, 20, 30, 40, 50 };

    // Second array
    int second[] = { 1, 2, 3, 4, 5 };

    // Result array
    int results[5];

    // std::transform applies std::divides to the whole array
    std::transform(first, first + 5, second, results, std::divides<int>());

    // Printing the result array
    for (int i = 0; i < 5; i++)
        std::cout << results[i] << " ";

    return 0;
}
```

输出:

```cpp
10 10 10 10 10
```

**另一个例子:**

```cpp
// C++ program to illustrate std::divides
// by dividing all array elements with a number
#include <bits/stdc++.h>

int main()
{
    // Array with elements to be divided
    int arr[] = { 10, 10 };

    // size of array
    int size = sizeof(arr) / sizeof(arr[0]);

    // Variable with which array is to be divided
    int num = 100;

    // Variable to store result
    int result;

    // using std::accumulate to perform division on array with num
    // using std::divides
    result = std::accumulate(arr, arr + size, num, std::divides<int>());

    // Printing the result
    std::cout << "The result of (100 / 10) / 10 is " << result;

    return 0;
}
```

输出:

```cpp
The result of (100 / 10) / 10 is 1

```

本文由 **Rohit Thapliyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。