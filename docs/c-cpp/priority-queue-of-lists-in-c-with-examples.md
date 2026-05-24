# c++ 中列表的优先级队列，示例

> 原文:[https://www . geesforgeks . org/priority-queue-of-list-in-c-with-examples/](https://www.geeksforgeeks.org/priority-queue-of-lists-in-c-with-examples/)

**<u>优先队列</u>**

[**<u>【优先级队列】</u>**](https://www.geeksforgeeks.org/priority-queue-in-cpp-stl/) 是一种容器适配器，专门设计为队列的第一个元素是队列中所有元素中最大的，元素的顺序不递增(因此我们可以看到队列的每个元素都有优先级{固定顺序})。

**与优先级队列一起使用的函数:**

*   **empty():** 此函数返回队列是否为空。
*   **size():** 这个函数返回队列的大小。
*   **top():** 返回对队列最顶端元素的引用。
*   **push(x):** 这个函数在队列的末尾添加元素‘x’。

**<u>列出</u>**

[**<u>列表</u>**](https://www.geeksforgeeks.org/list-cpp-stl/) 是允许非连续内存分配的序列容器。与 vector 相比，列表遍历速度慢，但是一旦找到位置，插入和删除就很快。通常，当我们说一个列表时，我们说的是一个双重链表。为了实现单链表，我们使用了一个转发列表。

**与列表一起使用的功能:**

*   **push_front(x):** 在列表的开头添加一个新元素‘x’。
*   **push_back(x):** 在列表末尾添加新元素‘x’。

**<u>转发列表</u>**

[**<u>正向列表</u>**](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/) 在 STL 中实现单链表。前向列表是从 C++ 11 引入的，在插入、移除和移动操作(如排序)方面比其他容器更有用，并且允许元素的时间常数插入和移除。与列表的不同之处在于前进列表仅跟踪下一个元素的位置，而列表跟踪下一个和上一个元素的，从而增加了存储每个元素所需的存储空间。 a 正向列表的缺点是不能迭代反向并且不能直接访问其单个元素。
当只需要正向遍历时，正向列表优于列表(与单链表优于双链表相同)，这样可以节省空间。一些例子是，散列中的链接，图的邻接表表示等。

**与转发列表一起使用的功能:**

*   **push_front(x):** 在列表的开头添加一个新元素‘x’。

本文主要讨论如何在 C++ 中使用转发列表和列表的优先级队列。列表和转发列表的优先级队列在设计复杂的数据结构时非常有用。

下面是转发列表优先级队列的实现:

## C++

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to print priority queue
// contents. Deliberately passing it
// call by value since we don't want
// to remove elements from the priority
// queue
void print(priority_queue<forward_list<int> > priorityQueue)
{
    while (!priorityQueue.empty()) {
        // Each element of the priority
        // queue is a forward list itself
        forward_list<int> st = priorityQueue.top();

        cout << "[ ";

        // Print the forward list elements
        for (auto element : st)
            cout << element << ' ';
        cout << ']';
        cout << '\n';

        // Pop out the topmost forward
        // list
        priorityQueue.pop();
    }
}

// Driver code
int main()
{
    // Declaring a priority queue of
    // forward list
    priority_queue<forward_list<int> > priorityQueue;

    // Declaring a forward list
    forward_list<int> forwardList1;

    // Inserting into the forward list
    forwardList1.push_front(2);
    forwardList1.push_front(4);
    forwardList1.push_front(6);

    // Inserting the forward list into
    // the priority queue
    priorityQueue.push(forwardList1);

    // Declaring another forward list
    forward_list<int> forwardList2;

    // Inserting into the forward list
    forwardList2.push_front(1);
    forwardList2.push_front(3);
    forwardList2.push_front(7);

    // Inserting the forward list into
    // the priority queue
    priorityQueue.push(forwardList2);

    // Declaring another forward list
    forward_list<int> forwardList3;

    // Inserting into the forward list
    forwardList3.push_front(11);
    forwardList3.push_front(22);
    forwardList3.push_front(33);

    // Inserting the forward list into
    // the priority queue
    priorityQueue.push(forwardList3);

    // Calling print function
    print(priorityQueue);

    return 0;
}
```

**Output**

```cpp
[ 33 22 11 ]
[ 7 3 1 ]
[ 6 4 2 ]
```

下面是列表优先级队列的实现:

## C++

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to print priority queue
// contents. Deliberately passing it
// call by value since we don't want
// to remove elements from the priority
// queue
void print(priority_queue<list<int> > priorityQueue)
{
    while (!priorityQueue.empty()) {
        // Each element of the priority
        // queue is a list itself
        list<int> st = priorityQueue.top();

        cout << "[ ";

        // Print the list elements
        for (auto element : st)
            cout << element << ' ';

        cout << ']';
        cout << '\n';

        // Pop out the topmost list
        priorityQueue.pop();
    }
}

// Driver code
int main()
{
    // Declaring a priority queue of
    // lists
    priority_queue<list<int> > priorityQueue;

    // Declaring a list
    list<int> list1;

    // Inserting into the list
    // Pushing at the front in the
    list1.push_front(2);

    // Pushing at the back in the
    // list
    list1.push_back(4);
    list1.push_back(6);

    // Inserting the list into the
    // priority queue
    priorityQueue.push(list1);

    // Declaring another list
    list<int> list2;

    // Inserting into the list
    // Pushing at the front in the
    list2.push_front(2);

    // Pushing at the back in the
    // list
    list2.push_back(4);
    list2.push_back(7);

    // Inserting the list into the
    // priority queue
    priorityQueue.push(list2);

    // Declaring another list
    list<int> list3;

    // Inserting into the list

    // Pushing at the front in the
    list3.push_front(11);

    // Pushing at the back in the
    // list
    list3.push_back(22);
    list3.push_back(33);

    // Inserting the list into the
    // priority queue
    priorityQueue.push(list3);

    // Calling print function
    print(priorityQueue);

    return 0;
}
```

**Output**

```cpp
[ 11 22 33 ]
[ 2 4 7 ]
[ 2 4 6 ]
```

默认情况下，优先级队列是最大堆，因此对于优先级队列中的两个列表/转发列表，具有最大第一个元素的列表/转发列表是最顶端的元素。如果第一个元素相等，则比较列表/转发列表的第二个值，以此类推。