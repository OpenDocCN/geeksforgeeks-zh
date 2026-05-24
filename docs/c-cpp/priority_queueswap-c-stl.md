# c++ STL 中的 priority _ queue::swap()

> 原文:[https://www.geeksforgeeks.org/priority_queueswap-c-stl/](https://www.geeksforgeeks.org/priority_queueswap-c-stl/)

[优先级队列](https://www.geeksforgeeks.org/priority-queue-in-cpp-stl/)是一种容器适配器，专门设计为队列的第一个元素是队列中所有元素中最大的。

**priority_queue::swap()**

此功能用于将一个优先级队列的内容与另一个相同类型和大小的优先级队列进行交换。

**语法:**

```cpp
*priorityqueuename1*.swap(*priorityqueuename2*)
Parameters :
The name of the priority queue with which
the contents have to be swapped.
Result :
All the elements of the 2 priority queues are swapped.

```

示例:

```cpp
Input  : mypqueue1 = {1, 2, 3, 4}
         mypqueue2 = {3, 5, 7, 9}
         mypqueue1.swap(mypqueue2);
Output : mypqueue1 = {9, 7, 5, 3}
         mypqueue2 = {4, 3, 2, 1}

Input  : mypqueue1 = {1, 3, 5, 7}
         mypqueue2 = {2, 4, 6, 8}
         mypqueue1.swap(mypqueue2);
Output : mypqueue1 = {8, 6, 4, 2}
         mypqueue2 = {7, 5, 3, 1}

```

```cpp
Note: In priority_queue container, the elements are printed
      in reverse order because the top is printed first
      then moving on to other elements.

```

**错误和异常**

1.如果优先级队列不是同一类型，它将引发错误。
2。否则它有一个基本的无异常抛出保证。

```cpp
// CPP program to illustrate
// Implementation of swap() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    // priority_queue container declaration
    priority_queue<int> mypqueue1;
    priority_queue<int> mypqueue2;

    // pushing elements into the 1st priority queue
    mypqueue1.push(1);
    mypqueue1.push(2);
    mypqueue1.push(3);
    mypqueue1.push(4);

    // pushing elements into the 2nd priority queue
    mypqueue2.push(3);
    mypqueue2.push(5);
    mypqueue2.push(7);
    mypqueue2.push(9);

    // using swap() function to swap elements of priority queues
    mypqueue1.swap(mypqueue2);

    // printing the first priority queue
    cout << "mypqueue1 = ";
    while (!mypqueue1.empty()) {
        cout << mypqueue1.top() << " ";
        mypqueue1.pop();
    }

    // printing the second priority queue
    cout << endl
         << "mypqueue2 = ";
    while (!mypqueue2.empty()) {
        cout << mypqueue2.top() << " ";
        mypqueue2.pop();
    }
    return 0;
}
```

输出:

```cpp
mypqueue1 = 9 7 5 3 
mypqueue2 = 4 3 2 1 

```