# C++ STL 中的 `deque::front()` 和 `deque::back()`

> 原文链接：[https://www.geeksforgeeks.org/deque-front-deque-back-cpp-stl/](https://www.geeksforgeeks.org/deque-front-deque-back-cpp-stl/)

Deque 或双端队列是一种序列容器，具有在两端进行伸缩的特性。它们类似于向量，但在开头插入和删除元素的情况下，以及在末尾插入和删除元素的情况下，效率更高。与向量不同，连续的存储分配可能无法在 `deque` 中得到保证。

## `deque::front()`

`front()` 用于引用 `deque` 容器的第一个元素。这个函数可以用来获取一个 `deque` 的第一个元素。这是来自 [C++ 标准模板库 (STL)](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的内置函数。该功能属于 `<deque>` 头文件。

**语法：**

```cpp
dequename.front()
```

**返回：** 直接引用 `deque` 容器的第一个元素。

**示例：**

```cpp
Input  :  mydeque = 1, 2, 3
          mydeque.front();
Output :  1

Input  :  mydeque = 3, 4, 1, 7, 3
          mydeque.front();
Output :  3
```

**错误和异常：**

1.  如果 `deque` 容器是空的，它会导致未定义的行为。
2.  如果 `deque` 不是空的，它有一个无异常抛出保证。

```cpp
// CPP program to demonstrate
// Implementation of front() function
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    deque<int> mydeque;
    mydeque.push_back(3);
    mydeque.push_back(4);
    mydeque.push_back(1);
    mydeque.push_back(7);
    mydeque.push_back(3);
    // Queue becomes 3, 4, 1, 7, 3

    cout << mydeque.front();
    return 0;
}
```

**Output**

```cpp

```

## `deque::back()`

`back()` 函数用于引用 `deque` 容器的最后一个元素。这个函数可以用来从 `deque` 的后面获取元素。这是一个来自 C++ 标准模板库 (STL) 的内置函数。该功能属于 `<deque>` 头文件。

**语法：**

```cpp
dequename.back()
```

**返回：** 直接引用 `deque` 容器的最后一个元素。

**示例：**

```cpp
Input  :  mydeque = 1, 2, 3
          mydeque.back();
Output :  3

Input  :  mydeque = 3, 4, 1, 7, 3
          mydeque.back();
Output :  3
```

**错误和异常：**

1.  如果 `deque` 容器是空的，它会导致未定义的行为。
2.  如果 `deque` 不是空的，它有一个无异常抛出保证。

```cpp
// CPP program to demonstrate
// Implementation of back() function
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    deque<int> mydeque;
    mydeque.push_back(3);
    mydeque.push_back(4);
    mydeque.push_back(1);
    mydeque.push_back(7);
    mydeque.push_back(3);
    // Queue becomes 3, 4, 1, 7, 3

    cout << mydeque.back();
    return 0;
}
```

**Output**

```cpp

```

## 应用：`deque::front()` 和 `deque::back()`

给定一个空的整数 `deque`，将数字加到 `deque` 上，然后打印第一个和最后一个元素之间的差。

```cpp
Input  : 1, 2, 3, 4, 5, 6, 7, 8
Output : 7
```

（**说明**：最后一个元素是 8，第一个元素是 1，差会是 7）

**算法：**

1.  使用 `push_back()` 功能，将数字添加到 `deque` 中。
2.  比较第一个和最后一个元素。
3.  如果第一个元素较大，则减去最后一个元素并打印出来。
4.  否则从最后一个元素中减去第一个元素并打印出来。

```cpp
// CPP program to demonstrate
// application Of front() and back() function
#include <deque>
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    deque<int> mydeque;
    mydeque.push_back(8);
    mydeque.push_back(7);
    mydeque.push_back(6);
    mydeque.push_back(5);
    mydeque.push_back(4);
    mydeque.push_back(3);
    mydeque.push_back(2);
    mydeque.push_back(1);
    // deque becomes 8, 7, 6, 5, 4, 3, 2, 1

    if (mydeque.front() > mydeque.back()) {
        cout << mydeque.front() - mydeque.back();
    }
    else if (mydeque.front() < mydeque.back()) {
        cout << mydeque.back() - mydeque.front();
    }
    else
        cout << "0";

    return 0;
}
```

**Output**

```cpp

```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。