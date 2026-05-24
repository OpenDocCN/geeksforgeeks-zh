# STD::c++ 中的减号

> 原文:[https://www.geeksforgeeks.org/stdminus-in-c/](https://www.geeksforgeeks.org/stdminus-in-c/)

二进制函数对象类，其调用返回第一个参数减去第二个参数的结果(由二进制运算符-返回)。

**语法:**

```cpp
template  struct minus : binary_function  
{
  T operator() (const T& x, const T& y) const {return x-y;}
};

Template parameters :
T - Type of the arguments and return type of the functional call.
    The type shall support the operation (binary operator-).

Member types :
x : Type of the first argument in member operator()
y : Type of the second argument in member operator()
result_type : Type returned by member operator()

```

```cpp
// C++ program to illustrate std::minus
// by subtracting all array elements from a number
#include <bits/stdc++.h>

int main()
{
    // Array with elements to be subtracted
    int arr[] = { 10, 20, 30 };

    // size of array
    int size = sizeof(arr) / sizeof(arr[0]);

    // Variable from which array is to be subtracted
    int num = 100;

    // Variable to store result
    int result;

    // using std::accumulate to perform subtraction on array from num
    // using std::minus
    result = std::accumulate(arr, arr + size, num, std::minus<int>());

    // Printing the result
    std::cout << "The result of 100-10-20-30 is " << result;

    return 0;
}
```

输出:

```cpp
The result of 100-10-20-30 is 40
```

**另一个例子:**

```cpp
// C++ program to illustrate std::minus
// by subtracting the respective elements of 2 arrays
#include <iostream> // std::cout
#include <functional> // std::plus
#include <algorithm> // std::transform

int main()
{
    // First array
    int first[] = { 100, 200, 300, 400, 500 };

    // Second array
    int second[] = { 10, 20, 30, 40, 50 };

    // Result array
    int results[5];

    // std::transform applies std::minus to the whole array
    std::transform(first, first + 5, second, results, std::minus<int>());

    // Printing the result array
    for (int i = 0; i < 5; i++)
        std::cout << results[i] << " ";

    return 0;
}
```

输出:

```cpp
90 180 270 360 450

```

本文由 **Rohit Thapliyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。