# c++ 标准模板库(STL)中的优先级队列

> 原文:[https://www.geeksforgeeks.org/priority-queue-in-cpp-stl/](https://www.geeksforgeeks.org/priority-queue-in-cpp-stl/)

优先级队列是[容器适配器](https://www.geeksforgeeks.org/containers-cpp-stl/)的一种类型，专门设计为队列的第一个元素是队列中所有元素中最大的，元素的顺序不递增(因此我们可以看到队列的每个元素都有优先级{固定顺序})。下面是一个演示优先级队列及其各种方法的示例。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP Program to demonstrate Priority Queue
#include <iostream>
#include <queue>
using namespace std;

void showpq(priority_queue<int> gq)
{
    priority_queue<int> g = gq;
    while (!g.empty()) {
        cout << '\t' << g.top();
        g.pop();
    }
    cout << '\n';
}

// Driver Code
int main()
{
    priority_queue<int> gquiz;
    gquiz.push(10);
    gquiz.push(30);
    gquiz.push(20);
    gquiz.push(5);
    gquiz.push(1);

    cout << "The priority queue gquiz is : ";
    showpq(gquiz);

    cout << "\ngquiz.size() : " << gquiz.size();
    cout << "\ngquiz.top() : " << gquiz.top();

    cout << "\ngquiz.pop() : ";
    gquiz.pop();
    showpq(gquiz);

    return 0;
}
```

**Output**

```cpp
The priority queue gquiz is :     30    20    10    5    1

gquiz.size() : 5
gquiz.top() : 30
gquiz.pop() :     20    10    5    1
```

> **注意:**默认情况下，C++ 为优先级队列创建最大堆。

**如何为优先级队列创建最小堆？**

C++ 提供了相同的语法。

**语法:**

```cpp
priority_queue <int, vector<int>, greater<int>> g = gq;  
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate min heap for priority queue
#include <iostream>
#include <queue>
using namespace std;

void showpq(
    priority_queue<int, vector<int>, greater<int> > gq)
{
    priority_queue<int, vector<int>, greater<int> > g = gq;
    while (!g.empty()) {
        cout << '\t' << g.top();
        g.pop();
    }
    cout << '\n';
}

// Driver Code
int main()
{
    priority_queue<int, vector<int>, greater<int> > gquiz;
    gquiz.push(10);
    gquiz.push(30);
    gquiz.push(20);
    gquiz.push(5);
    gquiz.push(1);

    cout << "The priority queue gquiz is : ";
    showpq(gquiz);

    cout << "\ngquiz.size() : " << gquiz.size();
    cout << "\ngquiz.top() : " << gquiz.top();

    cout << "\ngquiz.pop() : ";
    gquiz.pop();
    showpq(gquiz);

    return 0;
}
```

**Output**

```cpp
The priority queue gquiz is :     1    5    10    20    30

gquiz.size() : 5
gquiz.top() : 1
gquiz.pop() :     5    10    20    30
```

> **注意:**上面的语法可能比较难记，所以在数值的情况下，我们可以将数值乘以-1，使用 max heap 得到 min heap 的效果。

**优先级队列的方法有:**

<figure class="table">

| 

方法

 | 

定义

 |
| --- | --- |
| [优先级 _queue::empty()](https://www.geeksforgeeks.org/priority_queueempty-priority_queuesize-c-stl/) | Returns whether the queue is empty. |
| [priority _ queue::size()](https://www.geeksforgeeks.org/priority_queueempty-priority_queuesize-c-stl/) | Returns the size of the queue. |
| [priority _ queue::top()](https://www.geeksforgeeks.org/priority_queuetop-c-stl/) | Returns a reference to the top element of the queue. |
| [priority _ queue::push()](https://www.geeksforgeeks.org/priority_queuepush-priority_queuepop-c-stl/) | The element' g' was added at the end of the queue. |
| [priority _ queue::pop()](https://www.geeksforgeeks.org/priority_queuepush-priority_queuepop-c-stl/) | Delete the first element of the queue. |
| [priority _ queue::swap()](https://www.geeksforgeeks.org/priority_queueswap-c-stl/) | Used to exchange the contents of one priority queue with another priority queue of the same type and size. |
| [priority _queue:: gun position ()](https://www.geeksforgeeks.org/priority_queue-emplace-in-cpp-stl/) | Used to insert a new element into the priority queue container. |
| [优先级 _ 队列值 _ 类型](https://www.geeksforgeeks.org/priority_queue-value_type-in-c-stl/) | Indicates the type of object stored as an element in priority _ queue. It acts as a synonym for template parameters. |

</figure>

**必读:** [**近期 STL**](https://www.geeksforgeeks.org/tag/cpp-priority-queue/) 优先排队文章

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。