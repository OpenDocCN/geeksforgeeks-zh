# C++ 中集合的优先级队列，示例

> 原文：[https://www.geeksforgeeks.org/priority-queue-of-sets-in-c-with-examples/](https://www.geeksforgeeks.org/priority-queue-of-sets-in-c-with-examples/)

## 优先队列

[优先级队列](https://www.geeksforgeeks.org/priority-queue-in-cpp-stl/) 是一种容器适配器，专门设计为队列的第一个元素是队列中所有元素中最大的，元素的顺序不递增（因此我们可以看到队列的每个元素都有优先级{固定顺序}）。

## 与优先级队列一起使用的函数

*   `Empty()`: 返回队列是否为空。
*   `size()`: 返回队列的大小。
*   `top()`: 返回队列顶部元素的引用。
*   `pop()`: 删除队列的第一个元素。

## 集合

[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)是一种关联容器，其中每个元素必须是唯一的，因为元素的值标识了它。元素的值一旦被添加到集合中就不能被修改，尽管可以移除和添加该元素的修改值。

## 与集合一起使用的函数

*   `size()`: 返回集合中的元素数量。
*   `insert(const x)`: 向集合中添加一个新元素 `x`。

集合的优先级队列对于设计复杂的数据结构非常有用。

## 语法

```cpp
priority_queue<set<data_type>> priorityQueue
```
这将集合存储为最大堆优先级队列中的一个元素。

## 最大堆优先级队列的实现

下面是最大堆优先级队列的实现集：

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to print priority
// queue contents
void print(priority_queue<set<int> > priorityQueue)
{
    while (!priorityQueue.empty()) {
        // Each element of the priority
        // queue is a set itself
        set<int> st = priorityQueue.top();

        cout << "[ ";

        // Print the set elements
        for (auto element : st)
            cout << element << ' ';
        cout << ']';
        cout << '\n';

        // Pop out the topmost set
        priorityQueue.pop();
    }
}

// Driver code
int main()
{
    // Declaring a max-heap priority
    // queue
    priority_queue<set<int> > priorityQueue;

    // Declaring a set of integers
    set<int> set1;

    // Inserting into the set
    set1.insert(10);
    set1.insert(1);
    set1.insert(2);
    set1.insert(5);

    // Push the set into priority
    // queue
    priorityQueue.push(set1);

    // Declaring another set
    set<int> set2;

    // Inserting into the set
    set2.insert(2);
    set2.insert(7);
    set2.insert(12);
    set2.insert(1);

    // Push the set into priority queue
    priorityQueue.push(set2);

    // Declaring another set
    set<int> set3;

    // Inserting into the set
    set3.insert(4);
    set3.insert(7);
    set3.insert(12);
    set3.insert(13);

    // Push the set into priority queue
    priorityQueue.push(set3);

    // Print the priority queue
    print(priorityQueue);

    return 0;
}
```

### 输出

```cpp
[ 4 7 12 13 ]
[ 1 2 7 12 ]
[ 1 2 5 10 ]
```

默认情况下，优先级队列是最大堆，因此对于优先级队列内部的两个集合，具有较大第一元素的集合是最顶端的元素。如果第一个元素相等，则比较集合的第二个值，以此类推。

## 语法

```cpp
priority_queue<set<data_type>, vector<set<data_type>>, greater<set<data_type>>> priorityQueue
```
这将集合存储为最小堆优先级队列中的一个元素。

## 最小堆优先级队列的实现

下面是最小堆优先级队列的实现集合：

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to print priority
// queue contents
void print(priority_queue<set<int>,
                         vector<set<int> >,
                         greater<set<int> > >
               priorityQueue)
{
    while (!priorityQueue.empty()) {
        // Each element of the priority
        // queue is a set itself
        set<int> st = priorityQueue.top();

        cout << "[ ";

        // Print the set elements
        for (auto element : st)
            cout << element << ' ';

        cout << ']';
        cout << '\n';

        // Pop out the topmost set
        priorityQueue.pop();
    }
}

// Driver code
int main()
{
    // Declaring a min-heap
    // priority queue
    priority_queue<set<int>,
                   vector<set<int> >,
                   greater<set<int> > >
        priorityQueue;

    // Declaring a set of integers
    set<int> set1;

    // Inserting into the set
    set1.insert(10);
    set1.insert(1);
    set1.insert(2);
    set1.insert(5);

    // Push the set into priority
    // queue
    priorityQueue.push(set1);

    // Declaring another set
    set<int> set2;

    // Inseting into the set
    set2.insert(2);
    set2.insert(7);
    set2.insert(12);
    set2.insert(1);

    // Push the set into priority
    // queue
    priorityQueue.push(set2);

    // Declaring another set
    set<int> set3;

    // Inserting into the set
    set3.insert(4);
    set3.insert(7);
    set3.insert(12);
    set3.insert(13);

    // Push the set into priority
    // queue
    priorityQueue.push(set3);

    // Print the priority queue
    print(priorityQueue);

    return 0;
}
```

### 输出

对于最小堆优先级队列中的两个集合，具有较小的第一个元素的集合是最顶端的元素。如果第一个元素相等，则比较集合的第二个值，以此类推。