# c++ STL 中的 priority_queue::empty()和 priority_queue::size()

> 原文:[https://www . geesforgeks . org/priority _ queue empty-priority _ queue size-c-STL/](https://www.geeksforgeeks.org/priority_queueempty-priority_queuesize-c-stl/)

[优先级队列](https://www.geeksforgeeks.org/priority-queue-in-cpp-stl/)是一种容器适配器，专门设计为队列的第一个元素是队列中最大的元素。

**priority_queue::empty()**

empty()函数用于检查优先级队列容器是否为空。

**语法:**

```cpp
*pqueuename*.empty()
Parameters :
No parameters are passed
Returns :
True, if priority queue is empty, 
False, Otherwise

```

示例:

```cpp
Input :  pqueue = 3, 2, 1
         pqueue.empty();
Output : False

Input :  pqueue
         pqueue.empty();
Output : True

```

**错误和异常**

1.如果参数通过
2，显示错误。显示无异常抛出保证。

```cpp
// CPP program to illustrate
// Implementation of empty() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    priority_queue<int> pqueue;
    pqueue.push(1);

    // Priority Queue becomes 1

    if (pqueue.empty()) {
        cout << "True";
    }
    else {
        cout << "False";
    }
    return 0;
}
```

输出:

```cpp
False

```

**应用**:给定一个整数的优先级队列，求所有整数的和。

```cpp
Input  : 8, 6, 3, 2, 1 
Output : 20

```

**算法**
1。检查优先级队列是否为空，如果不是，将顶部元素添加到初始化为 0 的变量中，并弹出顶部元素。
2。重复此步骤，直到优先级队列为空。
3。打印变量的最终值。

```cpp
// CPP program to illustrate
// Application of empty() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    int sum = 0;
    priority_queue<int> pqueue;
    pqueue.push(8);
    pqueue.push(6);
    pqueue.push(3);
    pqueue.push(2);
    pqueue.push(1);

    // Queue becomes 8, 6, 3, 2, 1

    while (!pqueue.empty()) {
        sum = sum + pqueue.top();
        pqueue.pop();
    }
    cout << sum;
    return 0;
}
```

输出:

```cpp
20

```

**priority_queue::size()**

size()函数用于返回优先级队列容器的大小或容器中元素的数量。

**语法:**

```cpp
*pqueuename*.size()
Parameters :
No parameters are passed
Returns :
Number of elements in the container

```

示例:

```cpp
Input :  pqueue = 3, 2, 1
         pqueue.size();
Output : 3

Input :  pqueue
         pqueue.size();
Output : 0

```

**错误和异常**

1.如果传递参数，则显示错误。
2。显示无异常抛出保证

```cpp
// CPP program to illustrate
// Implementation of size() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    int sum = 0;
    priority_queue<int> pqueue;
    pqueue.push(8);
    pqueue.push(6);
    pqueue.push(3);
    pqueue.push(3);
    pqueue.push(1);

    // Priority Queue becomes 8, 6, 3, 2, 1

    cout << pqueue.size();

    return 0;
}
```

输出:

```cpp
5

```

**应用**:给定一个整数的优先级队列，求所有整数的和。

```cpp
Input  : 8, 6, 3, 2, 1 
Output : 20

```

**算法**
1。检查优先级队列的大小是否为 0，如果不是，将顶部元素添加到初始化为 0 的变量中，并弹出顶部元素。
2。重复此步骤，直到优先级队列的大小变为 0。
3。打印变量的最终值。

```cpp
// CPP program to illustrate
// Application of size() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    int sum = 0;
    priority_queue<int> pqueue;
    pqueue.push(8);
    pqueue.push(6);
    pqueue.push(3);
    pqueue.push(2);
    pqueue.push(1);

    // Queue becomes 8, 6, 3, 2, 1

    while (pqueue.size() > 0) {
        sum = sum + pqueue.top();
        pqueue.pop();
    }
    cout << sum;
    return 0;
}
```

输出:

```cpp
20

```