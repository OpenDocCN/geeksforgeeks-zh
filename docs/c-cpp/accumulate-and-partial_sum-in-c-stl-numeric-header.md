# 在 C++ STL 中累加()和 partial_sum():数值头

> 原文:[https://www . geeksforgeeks . org/great-and-partial _ sum-in-c-STL-numeric-header/](https://www.geeksforgeeks.org/accumulate-and-partial_sum-in-c-stl-numeric-header/)

这个标题是 C++ STL 中数值库的一部分。本文解释了数字标题中的一些有用功能，这些功能可以在竞争性编程中使用，以节省时间和精力。

我们通常使用线性运算来找出特定范围或完整数组中的元素之和，这需要逐一添加该范围中的所有元素，并在每次迭代后将其存储到某个变量中。

**累加()**

该函数用变量 sum 返回位于**【第一个，最后一个】**之间的所有值的总和。

1.  **语法 1:**

    ```cpp
    accumulate(first, last, sum);
    first, last : first and last elements of range 
                  whose elements are to be added
    sum :  initial value of the sum

    ```

2.  **语法 2:** 该函数返回变量 sum 位于[第一个，最后一个]之间的所有值的总和。

    ```cpp
    accumulate(first, last, sum, myfun); 
    myfun : a function for performing any 
            specific task. For example, we can
            find product of elements between
            first and last.

    ```

```cpp
// C++ program to demonstrate working of accumulate()
#include <iostream> 
#include <numeric>     
using namespace std;

// User defined function
int myfun(int x, int y) 
{
    // for this example we have taken product 
    // of adjacent numbers
    return x * y ;
}

int main() 
{
    // Initialize sum = 1 
    int sum = 1;
    int a[] = {5 , 10 , 15} ;

    // Simple default accumulate function
    cout << "\nResult using accumulate: ";
    cout << accumulate(a , a+3 , sum);

    // Using accumulate function with
    // defined function
    cout << "\nResult using accumulate with"
             "user-defined function: ";
    cout << accumulate(a, a+3, sum, myfun);

    // Using accumulate function with
    // pre-defined function 
    cout << "\nResult using accumulate with "
            "pre-defined function: ";
    cout << accumulate(a, a+3, sum, std::minus<int>());

    return 0;
}
```

输出:

```cpp
Result using accumulate: 31
Result using accumulate with user-defined function: 750
Result using accumulate with pre-defined function: -29

```

一道例题:[第 k1 个和第 k2 个最小元素之间所有元素的和](https://www.geeksforgeeks.org/sum-elements-k1th-k2th-smallest-elements/)

**partial_sum( )**

该函数将数组中相应元素的部分和赋给第二个数组的每个位置。它返回位于**【第一个，最后一个】**之间的所有值的部分和，并将其存储在另一个数组 b 中。
例如，如果 x 表示[第一个，最后一个]中的元素，y 表示结果中的元素，则 ys 可以计算为:

```cpp
y0 = x0 
y1 = x0 + x1 
y2 = x0 + x1 + x2 
y3 = x0 + x1 + x2 + x3 
y4 = x0 + x1 + x2 + x3 + x4

```

语法:

```cpp

partial_sum(first, last, b);
partial_sum(first, last, b, myfun);
first, last : first and last element of range 
              whose elements are to be added
b : index of array where  corresponding partial 
    sum will be stored;
myfun : a user defined function for performing 
        any specific task

```

```cpp
// C++ program to demonstrate working of accumulate()
#include <iostream> 
#include <numeric>     
using namespace std;

//user defined function
int myfun(int x, int y)
{
    // the sum of element is twice of its 
    // adjacent element
    return x + 2 * y;
}

int main () 
{
    int a[] = {1, 2, 3, 4, 5} ;
    int b[5];

    // Default function
    partial_sum(a , a+5 , b);

    cout << "Partial Sum - Using Default function: ";
    for (int i=0; i<5; i++)
        cout << b[i] << ' ';
    cout << '\n';

    // Using user defined function
    partial_sum(a , a+5 , b , myfun) ;

    cout << "Partial sum - Using user defined function: ";
    for (int i=0; i<5; i++)
        cout << b[i] << ' ';
    cout << '\n';

    return 0;
}
```

输出:

```cpp
Partial Sum - Using Default function: 1 3 6 10 15 
Partial sum - Using user defined function: 1 5 11 19 29 

```

本文由**阿比纳夫·蒂瓦里**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。