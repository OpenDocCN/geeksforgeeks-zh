# 伫列::位置()在 C++ STL

中

> 哎哎哎:# t0]https://www . geeksforgeeks . org/quequeuemplace-c-STL/

[队列](https://www.geeksforgeeks.org/queue-set-1introduction-and-array-implementation/)也是一种抽象数据类型或线性数据结构，它遵循执行操作的特定顺序。顺序是先进先出。在先进先出数据结构中，添加到队列中的第一个元素将是第一个被移除的元素。

**queue::emplace()**

这个函数用于向队列容器中插入一个新元素，新元素被添加到队列的末尾。
**语法:**

```cpp
***queuename***.emplace(***value***)
Parameters :
The element to be inserted into the queue
is passed as the parameter.

Result :
The parameter is added to the
forward list at the end.

```

示例:

```cpp
Input  : myqueue{1, 2, 3, 4, 5};
         myqueue.emplace(6);
Output : myqueue = 1, 2, 3, 4, 5, 6

Input  : myqueue{};
         myqueue.emplace(4);
Output : myqueue = 4

```

**错误和异常**
1。它有很强的异常保证，因此，如果抛出异常，不会进行任何更改。
2。参数应该与容器的类型相同，否则会引发错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// INTEGER queue EXAMPLE
// CPP program to illustrate
// Implementation of emplace() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    queue<int> myqueue;
    myqueue.emplace(1);
    myqueue.emplace(2);
    myqueue.emplace(3);
    myqueue.emplace(4);
    myqueue.emplace(5);
    myqueue.emplace(6);

    // queue becomes 1, 2, 3, 4, 5, 6

    while (!myqueue.empty())
    {
        cout << ' ' << myqueue.front();
        myqueue.pop();
    }
    return 0;
}
```

**输出:**

```cpp
1 2 3 4 5 6

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CHARACTER QUEUE EXAMPLE
// CPP program to illustrate
// Implementation of emplace() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    queue<char> myqueue;
    myqueue.emplace('k');
    myqueue.emplace('j');
    myqueue.emplace('y');
    myqueue.emplace('r');
    myqueue.emplace('y');
    myqueue.emplace('u');

    // queue becomes k, j, y, r, y, u

    while (!myqueue.empty())
    {
        cout << ' ' << myqueue.front();
        myqueue.pop();
    }
    return 0;
}
```

**输出:**

```cpp
k j y r y u

```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// STRING QUEUE EXAMPLE
// CPP program to illustrate
// Implementation of emplace() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    queue<string> myqueue;
    myqueue.emplace("This");
    myqueue.emplace("is");
    myqueue.emplace("a");
    myqueue.emplace("computer");
    myqueue.emplace("science");
    myqueue.emplace("portal");

    // queue becomes This, is, a, computer,
    //science, portal

    while (!myqueue.empty())
    {
        cout << ' ' << myqueue.front();
        myqueue.pop();
    }

    return 0;
}
```

**输出:**

```cpp
This is a computer science portal

```

**时间复杂度:**O(1)
T3】应用:输入一个空队列，求队列元素的和。

```cpp
Input :  7, 6, 4, 2, 7, 8
Output : 34 

```

**算法**
1。使用侵位()函数将元素插入队列。
2。检查队列是否为空，如果不是，将前端元素添加到 sum 变量并弹出它。
3。继续重复此步骤，直到队列变空
4。打印总和变量。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// application Of emplace() function
#include <queue>
#include <iostream>
using namespace std;

int main()
{
    // variable declaration
    int sum = 0;

    // queue declaration
    queue<int> myqueue{};

    // adding elements to the queue
    myqueue.emplace(7);
    myqueue.emplace(6);
    myqueue.emplace(4);
    myqueue.emplace(2);
    myqueue.emplace(7);
    myqueue.emplace(8);

    // queue becomes 7, 6, 4, 2, 7, 8

    // calculating the sum
    while (!myqueue.empty()) {
        sum = sum + myqueue.front();
        myqueue.pop();
    }
    cout<< sum;
}
```

**输出**

```cpp
34

```