# C++ STL 中的 `std::minmax()` 和 `std::minmax_element()`

> 原文: [https://www.geeksforgeeks.org/stdminmax-stdminmax_element-c-stl/](https://www.geeksforgeeks.org/stdminmax-stdminmax_element-c-stl/)

C++ 定义的函数使用不同的函数来获取 2 个或容器中的最小和最大元素。但是也有一些函数是使用单一函数来获得最小和最大元素的，`minmax()` 函数为我们完成了这个任务。该功能在 `algorithm` 头文件中定义。本文将讨论其实现和其他相关功能。

## `minmax()` 函数

### `minmax(a, b)`
此函数返回一个 `pair`，其中第一个元素是 `a` 和 `b` 两个元素中的最小值，第二个元素是 `a` 和 `b` 两个元素中的最大值。

### `minmax(元素数组)`
该函数返回类似于第一版。唯一不同的是，在这个版本中，接受的参数是整数/字符串列表，其中获得了最大值和最小值。在我们需要在列表中找到最大和最小元素而不排序的情况下很有用。

```cpp
// C++ code to demonstrate the working of minmax()
#include<iostream>
#include<algorithm>
using namespace std;

int main()
{
    // declaring pair to catch the return value
    pair<int, int> mnmx;

    // Using minmax(a, b)
    mnmx = minmax(53, 23);

    // printing minimum and maximum values
    cout << "The minimum value obtained is : ";
    cout << mnmx.first;
    cout << "\nThe maximum value obtained is : ";
    cout << mnmx.second ;

    // Using minmax(array of elements)
    mnmx = minmax({2, 5, 1, 6, 3});

    // printing minimum and maximum values.
    cout << "\n\nThe minimum value obtained is : ";
    cout << mnmx.first;
    cout << "\nThe maximum value obtained is : ";
    cout << mnmx.second;
}
```

输出:

```cpp
The minimum value obtained is : 23
The maximum value obtained is : 53

The minimum value obtained is : 1
The maximum value obtained is : 6
```

## `minmax_element()` 函数

`minmax_element()` 函数的目的与上述函数相同，即找到最小和最大元素。但它在返回类型和接受的参数上有所不同。该函数接受起始和结束指针作为参数，用于在某个范围内查找最大和最小元素。此函数返回一个 `pair` 迭代器，其第一个元素指向范围内最小元素的位置，第二个元素指向范围内最大元素的位置。如果最小值超过 1 个，第一个元素指向第一个出现的元素。如果最大值超过 1 个，第二个元素指向最后一个出现的元素。

```cpp
// C++ code to demonstrate the working of minmax_element()
#include<iostream>
#include<algorithm>
#include<vector>
using namespace std;

int main()
{
    // initializing vector of integers
    vector<int> vi = { 5, 3, 4, 4, 3, 5, 3 };

    // declaring pair pointer to catch the return value
    pair<vector<int>::iterator, vector<int>::iterator> mnmx;

    // using minmax_element() to find
    // minimum and maximum element
    // between 0th and 3rd number
    mnmx = minmax_element(vi.begin(), vi.begin() + 4);

    // printing position of minimum and maximum values.
    cout << "The minimum value position obtained is : ";
    cout << mnmx.first - vi.begin() << endl;

    cout << "The maximum value position obtained is : ";
    cout << mnmx.second - vi.begin() << endl;

    cout << endl;

    // using duplicated
    // prints 1 and 5 respectively
    mnmx = minmax_element(vi.begin(), vi.end());

    // printing position of minimum and maximum values.
    cout << "The minimum value position obtained is : ";
    cout << mnmx.first - vi.begin() << endl;

    cout << "The maximum value position obtained is : ";
    cout << mnmx.second - vi.begin()<< endl;
}
```

输出:

```cpp
The minimum value position obtained is : 1
The maximum value position obtained is : 0

The minimum value position obtained is : 1
The maximum value position obtained is : 5
```

本文由 **[【曼吉特·辛格】](https://github.com/Manjeet04)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。