# 在标准模板库中排队

> 哎哎哎:# t0]https://www . geeksforgeeks . org/queue-CPP-STL/

队列是一种容器适配器，以先进先出的方式工作。元素从后面(末端)插入，从前面删除。队列使用 [deque](https://www.geeksforgeeks.org/deque-cpp-stl/) 或 [list](https://www.geeksforgeeks.org/list-cpp-stl/) (顺序容器类)的封装对象作为其底层容器，提供一组特定的成员函数来访问其元素。

**队列支持的功能有:**

1.  [空()](https://www.geeksforgeeks.org/queueempty-queuesize-c-stl/)–返回队列是否为空。
2.  [size()](https://www.geeksforgeeks.org/queueempty-queuesize-c-stl/)–返回队列的大小。
3.  [队列::C++ STL 中的 swap()](https://www.geeksforgeeks.org/queue-swap-cpp-stl/):交换两个队列的内容，但是队列必须是同一类型，虽然大小可能不同。
4.  [队列::侵位()在 C++ STL 中](https://www.geeksforgeeks.org/queueemplace-c-stl/):在队列容器中插入一个新元素，新元素被添加到队列的末尾。
5.  [queue::front()和 queue::back()在 C++ STL 中](https://www.geeksforgeeks.org/queuefront-queueback-c-stl/)–**front()**函数返回对队列第一个元素的引用。 **back()** 函数返回对队列最后一个元素的引用。
6.  [push(g)和 pop()](https://www.geeksforgeeks.org/queuepush-and-queuepop-in-cpp-stl/)–**push()**函数在队列末尾添加元素“g”。 **pop()** 函数删除队列的第一个元素。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP code to illustrate
// Queue in Standard Template Library (STL)
#include <iostream>
#include <queue>

using namespace std;

// Print the queue
void showq(queue<int> gq)
{
    queue<int> g = gq;
    while (!g.empty()) {
        cout << '\t' << g.front();
        g.pop();
    }
    cout << '\n';
}

// Driver Code
int main()
{
    queue<int> gquiz;
    gquiz.push(10);
    gquiz.push(20);
    gquiz.push(30);

    cout << "The queue gquiz is : ";
    showq(gquiz);

    cout << "\ngquiz.size() : " << gquiz.size();
    cout << "\ngquiz.front() : " << gquiz.front();
    cout << "\ngquiz.back() : " << gquiz.back();

    cout << "\ngquiz.pop() : ";
    gquiz.pop();
    showq(gquiz);

    return 0;
}
```

**Output**

```cpp
The queue gquiz is :     10    20    30

gquiz.size() : 3
gquiz.front() : 10
gquiz.back() : 30
gquiz.pop() :     20    30
```

[**最近关于 C++ Queue 的文章**](https://www.geeksforgeeks.org/tag/cpp-queue/)

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论