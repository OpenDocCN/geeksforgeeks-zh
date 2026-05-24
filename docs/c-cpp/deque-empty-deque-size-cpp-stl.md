# c++ STL 中的 dequee::empty()和 dequee::size()

> 原文:[https://www . geesforgeks . org/deque-empty-deque-size-CPP-STL/](https://www.geeksforgeeks.org/deque-empty-deque-size-cpp-stl/)

[德清](https://www.geeksforgeeks.org/deque-cpp-stl/)或双端队列是顺序[集装箱](https://www.geeksforgeeks.org/containers-cpp-stl/)，具有两端伸缩的特点。它们类似于向量，但在末尾插入和删除元素的情况下，以及在开头插入和删除元素的情况下，效率更高。与向量不同，连续的存储分配可能无法在 deque 中得到保证。

### deqo::empty()

empty()函数用于检查 deque 容器是否为空。这是来自 [C++ 标准模板库(STL)](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的内置函数。该功能属于 **<德清>** 头文件。该功能返回**真**或**假**，具体取决于德格是否为空。
**语法:**

```cpp
dequename.empty()
```

**返回:**真，如果德格为空。假，否则

**示例:**

```cpp
Input :   mydeque
          mydeque.empty();
Output :  True

Input :   mydeque = 1, 2, 3
          mydeque.empty();
Output :  False
```

**错误和异常:**

*   如果参数被传递，则显示错误。
*   显示无异常抛出保证。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate
// Implementation of empty() function
#include <deque>
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    deque<int> mydeque;
    mydeque.push_front(1);

    // deque becomes 1
    if (mydeque.empty()) {
        cout << "True";
    }
    else {
        cout << "False";
    }
    return 0;
}
```

**Output**

```cpp
False
```

**应用:**德清::空()

给定一组整数，求所有整数的和。

```cpp
Input : 1, 8, 3, 6, 2
Output: 20
```

**算法:**

1.检查 deque 是否为空，如果不是，将 front 元素添加到初始化为 0 的变量中，并弹出 front 元素。
2。重复此步骤，直到 deque 为空。
3。打印变量的最终值。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate
// Application of empty() function
#include <deque>
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    int sum = 0;
    deque<int> mydeque;
    mydeque.push_back(1);
    mydeque.push_back(8);
    mydeque.push_back(3);
    mydeque.push_back(6);
    mydeque.push_back(2);
    // deque becomes 1, 8, 3, 6, 2

    while (!mydeque.empty()) {
        sum = sum + mydeque.front();
        mydeque.pop_front();
    }
    cout << sum;
    return 0;
}
```

**Output**

```cpp
20
```

### deque::size()

size()函数用于返回 deque 容器的大小或 deque 容器中的元素数量。这是一个来自 C++ 标准模板库(STL)的内置函数。该功能属于 **<德清>** 头文件。该函数要么返回一个数字，演示 deque 在该实例中持有的元素总数。
**语法:**

```cpp
dequename.size()
```

**返回:**容器中元素的数量。

**示例:**

```cpp
Input :   mydeque = 0, 1, 2
          mydeque.size();
Output :  3

Input :   mydeque = 0, 1, 2, 3, 4, 5
          mydeque.size();
Output :  6
```

**错误和异常:**

*   如果传递参数，则显示错误。
*   显示无异常抛出保证。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate
// Implementation of size() function
#include <deque>
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    int sum = 0;
    deque<int> mydeque;
    mydeque.push_back(1);
    mydeque.push_back(8);
    mydeque.push_back(3);
    mydeque.push_back(6);
    mydeque.push_back(2);
    // deque becomes 1, 8, 3, 6, 2

    cout << mydeque.size();

    return 0;
}
```

**Output**

```cpp
5
```

**应用:德格::大小()**

给定一组整数，求所有整数的和。

```cpp
Input : 1, 8, 3, 6, 2
Output: 20
```

**算法:**

1.检查 deque 的大小是否为零，如果不是，则将 front 元素添加到初始化为 0 的变量中，并弹出 front 元素。
2。重复此步骤，直到 deque 大小变为 0。
3。打印变量的最终值。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate
// Application of size() function
#include <deque>
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    int sum = 0;
    deque<int> mydeque;
    mydeque.push_back(1);
    mydeque.push_back(8);
    mydeque.push_back(3);
    mydeque.push_back(6);
    mydeque.push_back(2);
    // Deque becomes 1, 8, 3, 6, 2

    while (mydeque.size() > 0) {
        sum = sum + mydeque.front();
        mydeque.pop_front();
    }
    cout << sum;
    return 0;
}
```

**Output**

```cpp
20
```

> **注意:**基本上，**空()**功能检查德格的**大小()**是否为零。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。