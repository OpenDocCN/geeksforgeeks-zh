# 标准::C++ 17 中的夹钳

> 原文:[https://www.geeksforgeeks.org/stdclamp-in-cpp-17/](https://www.geeksforgeeks.org/stdclamp-in-cpp-17/)

将变量限制在给定范围内[高–低]。

```cpp
If num > high, num is assigned high.
If num < low, num is assigned low.
If num is already clamped, no modifications.
```

**注意:**这个函数从 C++ 17 开始在表头定义。

示例:

```cpp
Input : num = 100, Range : 10 - 90
Output : num = 90

Input : num = 5, Range : 10 - 90
Output : num = 10

Input : num = 50, Range : 10 - 90
Output : num = 50

```

**语法:**

```cpp
templateconstexpr const T& clamp( const T& num, const T& low, const T& high );
template
constexpr const T& clamp( const T& v, const T& lo, const T& hi, Compare comp );
Parameters
num      -    the value to clamp
low, high  -    the boundaries to clamp num to
comp      -    comparison function object which returns ?true if low is less than num
                and num is less than high. 

Return value
Reference to low if num is less than low,
Reference to high if high is less than num,
otherwise reference to num.

Applications :
To keep a list of inputs specified to a given range. 
Preventing size overflow.

```

```cpp
// CPP program to illustrate
// std::clamp
#include <bits/stdc++.h>

// Driver code
int main()
{
    // range [10 - 100]
    int high = 100, low = 10;

    // num1 higher than range
    int num1 = 120;

    // num2 lower than range
    int num2 = 5;

    // num3 in range
    int num3 = 50;

    // clamping all variables
    num1 = std::clamp(num1, low, high);
    num2 = std::clamp(num2, low, high);
    num3 = std::clamp(num3, low, high);

    // printing result
    std::cout << num1 << " " << num2 << " " << num3;
}
```

输出:

```cpp
100 10 50
```

```cpp
// CPP program to illustrate clamping
// array elements in given range
#include <iostream>
#include <algorithm>

// Range [30 - 60]
int low = 30, high = 60;

// Function to clamp the elements in given range
void clamp_arr_in_range(int arr[], int n)
{
    // Clamping the array elements
    for (int i = 0; i < n; i++) {
        arr[i] = std::clamp(arr[i], low, high);
    }
}

// Driver code
int main()
{
    // Array having elements to be clamped
    int arr[] = { 10, 20, 30, 40, 50, 60, 70, 80 };

    // Size of array
    int n = sizeof(arr) / sizeof(arr[0]);

    // Function call to clamp the elements
    clamp_arr_in_range(arr, n);

    // Printing the array
    for (int i = 0; i < n; i++)
        std::cout << arr[i] << " ";
}
```

输出:

```cpp
30 30 30 40 50 60 60 60

```

**带二元谓语**

```cpp
// C++ program to implement std::clamp
// with Binary Predicate

#include <bits/stdc++.h>

// Binary predicate
bool comp(int a, int b)
{
    return (a < b);
}

// Driver code
int main()
{
    // range [10 - 100]
    int high = 100, low = 10;

    // num1 higher than range
    int num1 = 120;

    // num2 lower than range
    int num2 = 5;

    // num3 in range
    int num3 = 50;

    // clamping all variables
    num1 = std::clamp(num1, low, high, comp);
    num2 = std::clamp(num2, low, high, comp);
    num3 = std::clamp(num3, low, high, comp);

    // printing result
    std::cout << num1 << " " << num2 << " " << num3;
}
```

输出:

```cpp
100 10 50
```

本文由 **Rohit Thapliyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。