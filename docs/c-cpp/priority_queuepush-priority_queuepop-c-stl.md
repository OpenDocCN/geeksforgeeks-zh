# c++ STL 中的 priority_queue::push()和 priority _ queue::pop()

> 原文:[https://www . geesforgeks . org/priority _ queuepush-priority _ queuepop-c-STL/](https://www.geeksforgeeks.org/priority_queuepush-priority_queuepop-c-stl/)

[优先级队列](https://www.geeksforgeeks.org/priority-queue-in-cpp-stl/)是一种容器适配器，专门设计为队列的第一个元素是队列中最大的元素。

**priority_queue::push()**

push()函数用于在优先级队列中插入一个元素。元素被添加到优先级队列容器中，队列的大小增加 1。首先，元素被添加到后面，同时优先级队列的元素根据优先级重新排序。

**语法:**

```cpp
*pqueuename*.push(*value*)
Parameters :
The value of the element to be inserted is passed as the parameter.
Result :
Adds an element of value same as that of 
the parameter passed in the priority queue.

```

示例:

```cpp
Input :  pqueue
         pqueue.push(6);
Output : 6

Input :  pqueue = 5, 2, 1
         pqueue.push(3);
Output : 5, 3, 2, 1

```

**错误和异常**

1.如果传递的值与优先级队列类型不匹配，则显示错误。
2。如果参数不抛出任何异常，则显示无异常抛出保证。

```cpp
// CPP program to illustrate
// Implementation of push() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    // Empty Queue
    priority_queue<int> pqueue;
    pqueue.push(3);
    pqueue.push(5);
    pqueue.push(1);
    pqueue.push(2);
    // Priority queue becomes 5, 3, 2, 1

    // Printing content of queue
    while (!pqueue.empty()) {
        cout << ' ' << pqueue.top();
        pqueue.pop();
    }
}
```

输出:

```cpp
5 3 2 1

```

**priority_queue::pop()**

pop()函数用于移除优先级队列的顶部元素。

**语法:**

```cpp
*pqueuename*.pop()
Parameters :
No parameters are passed.
Result :
The top element of the priority
queue is removed.

```

示例:

```cpp
Input :  pqueue = 3, 2, 1
         myqueue.pop();
Output : 2, 1

Input :  pqueue = 5, 3, 2, 1
         pqueue.pop();
Output : 3, 2, 1

```

**错误和异常**

1.如果传递参数，则显示错误。
2。如果参数不抛出任何异常，则显示无异常抛出保证。

```cpp
// CPP program to illustrate
// Implementation of pop() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    // Empty Priority Queue
    priority_queue<int> pqueue;
    pqueue.push(0);
    pqueue.push(1);
    pqueue.push(2);
    // queue becomes 2, 1, 0

    pqueue.pop();
    pqueue.pop();
    // queue becomes 0

    // Printing content of priority queue
    while (!pqueue.empty()) {
        cout << ' ' << pqueue.top();
        pqueue.pop();
    }
}
```

输出:

```cpp
0

```

**应用:push()和 pop()**
给定若干个整数，将它们加到优先级队列中，不用 size 函数就能求出优先级队列的大小。

```cpp
Input : 5, 13, 0, 9, 4
Output: 5

```

**算法**
1。将给定的元素逐个推送到优先级队列容器。
2。不断弹出优先级队列的元素，直到它变成空的，并增加计数器变量。
3。打印计数器变量。

```cpp
// CPP program to illustrate
// Application of push() and pop() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    int c = 0;
    // Empty Priority Queue
    priority_queue<int> pqueue;
    pqueue.push(5);
    pqueue.push(13);
    pqueue.push(0);
    pqueue.push(9);
    pqueue.push(4);
    // Priority queue becomes 13, 9, 5, 4, 0

    // Counting number of elements in queue
    while (!pqueue.empty()) {
        pqueue.pop();
        c++ ;
    }
    cout << c;
}
```

输出:

```cpp
5

```