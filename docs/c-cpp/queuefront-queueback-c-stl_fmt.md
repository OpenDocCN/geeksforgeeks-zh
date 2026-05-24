# C++ STL 中的 `queue::front()` 和 `queue::back()`

> 原文链接：[https://www.geeksforgeeks.org/queuefront-queueback-c-stl/](https://www.geeksforgeeks.org/queuefront-queueback-c-stl/)

[队列](https://www.geeksforgeeks.org/queue-cpp-stl/)是一种以先进先出（FIFO）方式运行的容器适配器。元素从后面（末端）插入，从前面删除。

## `queue::front()`

此函数用于引用队列容器的第一个或最旧的元素。这个函数可以用来获取队列的第一个元素。

**语法：**

```cpp
queuename.front()
```

**参数：**
不需要传递任何参数。

**返回值：**
直接引用队列容器的第一个元素。

**示例：**

```cpp
Input  :  myqueue = 1, 2, 3
          myqueue.front();
Output :  1

Input  :  myqueue = 3, 4, 1, 7, 3
          myqueue.front();
Output :  3
```

**错误和异常**

1.  如果队列容器为空，会导致未定义的行为。
2.  如果队列不是空的，它有一个无异常抛出保证。

### 代码示例

```cpp
// CPP program to illustrate
// Implementation of front() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    queue<int> myqueue;
    myqueue.push(3);
    myqueue.push(4);
    myqueue.push(1);
    myqueue.push(7);

    // Queue becomes 3, 4, 1, 7

    cout << myqueue.front();
    return 0;
}
```

**输出：**

```cpp
3
```

## `queue::back()`

该函数用于引用队列容器的最后一个或最新的元素。这个函数可以用来从队列的后面获取元素。

**语法：**

```cpp
queuename.back()
```

**参数：**
不需要传递任何参数。

**返回值：**
直接引用队列容器的最后一个元素。

**示例：**

```cpp
Input  :  myqueue = 1, 2, 3
          myqueue.back();
Output :  3

Input  :  myqueue = 3, 4, 1, 7, 3
          myqueue.back();
Output :  3
```

**错误和异常**

1.  如果队列容器为空，会导致未定义的行为。
2.  如果队列不是空的，它有一个无异常抛出保证。

### 代码示例

```cpp
// CPP program to illustrate
// Implementation of back() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    queue<int> myqueue;
    myqueue.push(3);
    myqueue.push(4);
    myqueue.push(1);
    myqueue.push(7);

    // Queue becomes 3, 4, 1, 7

    cout << myqueue.back();
    return 0;
}
```

**输出：**

```cpp
7
```

## 应用

给定一个空的整数队列，给队列加上数字，然后打印第一个元素和最后一个元素的差。

```cpp
Input  : 1, 2, 3, 4, 5, 6, 7, 8
Output : 7
```

**解释：** 最后一个元素 = 8，第一个元素 = 1，差值 = 7。

**算法：**

1.  使用 `push()` 功能向队列中添加号码。
2.  比较第一个和最后一个元素。
3.  如果第一个元素较大，减去最后一个元素并打印出来。
4.  否则从最后一个元素中减去第一个元素并打印出来。

### 代码示例

```cpp
// CPP program to illustrate
// application Of front() and back() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    queue<int> myqueue;
    myqueue.push(8);
    myqueue.push(7);
    myqueue.push(6);
    myqueue.push(5);
    myqueue.push(4);
    myqueue.push(3);
    myqueue.push(2);
    myqueue.push(1);

    // Queue becomes 1, 2, 3, 4, 5, 6, 7, 8

    if (myqueue.front() > myqueue.back()) {
        cout << myqueue.front() - myqueue.back();
    }
    else if (myqueue.front() < myqueue.back()) {
        cout << myqueue.back() - myqueue.front();
    }
    else
        cout << "0";
}
```

**输出：**

```cpp
7
```