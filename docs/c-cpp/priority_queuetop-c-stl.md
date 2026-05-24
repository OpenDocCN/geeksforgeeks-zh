# priority_queue::top()在 C++ STL 中

> 原文:[https://www.geeksforgeeks.org/priority_queuetop-c-stl/](https://www.geeksforgeeks.org/priority_queuetop-c-stl/)

[优先级队列](https://www.geeksforgeeks.org/priority-queue-in-cpp-stl/)是一种容器适配器，专门设计为队列的第一个元素是队列中最大的元素。

**priority_queue::top()**

top()函数用于引用优先级队列的顶部(或最大的)元素。
**语法:**

```cpp
*pqueuename*.top()
Parameters :
No value is needed to pass as the parameter.
Returns :
Direct reference to the top(or the largest)
element of the priority queue container.

```

示例:

```cpp
Input  : pqueue.push(5);
         pqueue.push(1);
         pqueue.top();
Output : 5

Input  : pqueue.push(5);
         pqueue.push(1);
         pqueue.push(7);
         pqueue.top();
Output : 7

```

**错误和异常**

1.如果优先级队列容器为空，会导致未定义的行为
2。如果优先级队列不为空，它保证无异常抛出

```cpp
// CPP program to illustrate
// Implementation of top() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    priority_queue<int> pqueue;
    pqueue.push(5);
    pqueue.push(1);
    pqueue.push(7);

    // Priority queue top
    cout << pqueue.top();
    return 0;
}
```

输出:

```cpp
7

```

**应用:**
给定整数的优先级队列，求素数和非素数的个数。

```cpp
Input : 8, 6, 3, 2, 1
Output: Prime - 2
        Non Prime - 3

```

**算法**
1。在变量中输入优先级队列的大小。
2。检查优先级队列是否为空，检查顶部元素是否为质数，质数增加质数计数器，弹出顶部元素。
3。重复此步骤，直到优先级队列为空。
4。打印变量质数和非质数(大小–质数)的最终值。

```cpp
// CPP program to illustrate
// Application of top() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    int prime = 0, nonprime = 0, size;
    priority_queue<int> pqueue;
    pqueue.push(1);
    pqueue.push(8);
    pqueue.push(3);
    pqueue.push(6);
    pqueue.push(2);
    size = pqueue.size();

    // Priority queue becomes 1, 8, 3, 6, 2

    while (!pqueue.empty()) {
        for (int i = 2; i <= pqueue.top() / 2; ++ i) {
            if (pqueue.top() % i == 0) {
                prime++ ;
                break;
            }
        }
        pqueue.pop();
    }
    cout << "Prime - " << prime << endl;
    cout << "Non Prime - " << size - prime;
    return 0;
}
```

输出:

```cpp
Prime - 2
Non Prime - 3

```