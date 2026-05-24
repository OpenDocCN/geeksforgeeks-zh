# 在 C++ STL 中对 push()和 pop()进行排队

> 原文:[https://www . geesforgeks . org/queue-push-and-queue-pop-in-CPP-STL/](https://www.geeksforgeeks.org/queue-push-and-queue-pop-in-cpp-stl/)

队列是一种以**先进先出(先进先出)**方式运行的容器。元素被插入到队列的后面(末尾)，并从队列的前面删除。

### 队列::推送()

push()函数用于在队列的后面插入一个元素。这是来自 [C++ 标准模板库(STL)](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) 的内置函数。该功能属于 **<队列>** 头文件。元素被添加到队列容器中，队列的大小增加 1。

**语法:**

```cpp
queuename.push(value)
```

**参数:**要插入的元素的值作为参数传递。

**结果:**添加一个与队列后面传递的参数值相同的元素。

**示例:**

```cpp
Input :  myqueue
         myqueue.push(6);
Output : 6

Input :  myqueue
         myqueue.push(0);
         myqueue.push(1);
Output : 0, 1
```

**错误和异常:**

1.  如果传递的值与队列类型不匹配，则显示错误。
2.  如果参数不抛出任何异常，则显示无异常抛出保证。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of push() function

#include <iostream>
#include <queue>
using namespace std;

int main()
{
    // Empty Queue
    queue<int> myqueue;
    myqueue.push(0);
    myqueue.push(1);
    myqueue.push(2);

    // Printing content of queue
    while (!myqueue.empty()) {
        cout << ' ' << myqueue.front();
        myqueue.pop();
    }
}
```

**Output**

```cpp
 0 1 2
```

> **注意:**这里输出是基于 **FIFO** 属性打印的。

### 伫列::pop()

pop()函数用于从队列前面移除一个元素(队列中最早的元素)。这是一个来自 C++ 标准模板库(STL)的内置函数。该功能属于 **<队列>** 头文件。元素从队列容器中移除，队列的大小减少 1。

**语法:**

```cpp
queuename.pop()
```

**参数:**没有参数通过

**结果:**移除队列中最早的元素或基本上最前面的元素。

**示例:**

```cpp
Input :  myqueue = 1, 2, 3
         myqueue.pop();
Output : 2, 3

Input :  myqueue = 3, 2, 1
         myqueue.pop();
Output : 2, 1
```

**错误和异常:**

1.  如果传递参数，则显示错误。
2.  如果参数不抛出任何异常，则显示无异常抛出保证。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of pop() function

#include <iostream>
#include <queue>
using namespace std;

int main()
{
    // Empty Queue
    queue<int> myqueue;
    myqueue.push(0);
    myqueue.push(1);
    myqueue.push(2);
    // queue becomes 0, 1, 2

    myqueue.pop();
    myqueue.pop();
    // queue becomes 2

    // Printing content of queue
    while (!myqueue.empty()) {
        cout << ' ' << myqueue.front();
        myqueue.pop();
    }
}
```

**Output**

```cpp
 2
```

> **注意:**这里输出是基于 **FIFO** 属性打印的。

### **应用:push()和 pop()**

给定一些整数，将它们添加到队列中，并在不使用 size 函数的情况下找到队列的大小。

```cpp
Input : 5, 13, 0, 9, 4
Output: 5
```

**算法:**

1。将给定的元素逐个推送到队列容器。
2。不断弹出队列的元素，直到队列变空，并增加计数器变量。
3。打印计数器变量。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Application of push() and pop() function

#include <iostream>
#include <queue>
using namespace std;

int main()
{
    // Empty Queue
    int c = 0;

    queue<int> myqueue;
    myqueue.push(5);
    myqueue.push(13);
    myqueue.push(0);
    myqueue.push(9);
    myqueue.push(4);
    // queue becomes 5, 13, 0, 9, 4

    // Counting number of elements in queue
    while (!myqueue.empty()) {
        myqueue.pop();
        c++ ;
    }
    cout << c;
}
```

**Output**

```cpp
5
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。