# c++ STL 中的 priority_queue 侵位()

> 原文:[https://www . geeksforgeeks . org/priority _ queue-place-in-CPP-STL/](https://www.geeksforgeeks.org/priority_queue-emplace-in-cpp-stl/)

[优先级队列](https://www.geeksforgeeks.org/priority-queue-in-cpp-stl/)是一种容器适配器，专门设计为队列的第一个元素是队列中所有元素中最大的。

**priority_queue::emplace()**

这个函数用于向优先级队列容器中插入一个新元素，这个新元素被添加到优先级队列的顶部。

**语法:**

```cpp
***priorityqueuename.emplace(value)***
Parameters :
The element to be inserted into the priority
queue is passed as the parameter.
Result :
The parameter is added to the
priority queue at the top position.
```

示例:

```cpp
Input  : mypqueue{5, 4};
         mypqueue.emplace(6);
Output : mypqueue = 6, 5, 4

Input  : mypqueue{};
         mypqueue.emplace(4);
Output : mypqueue = 4
```

**注意:**在 priority_queue 容器中，元素以相反的顺序打印，因为首先打印顶部，然后移动到其他元素。

**错误和异常**
1。它有很强的异常保证，因此，如果抛出异常，不会进行任何更改。
2。参数应该与容器的类型相同，否则会引发错误。

## C++

```cpp
// INTEGER PRIORITY QUEUE
// CPP program to illustrate
// Implementation of emplace() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    priority_queue<int> mypqueue;
    mypqueue.emplace(1);
    mypqueue.emplace(2);
    mypqueue.emplace(3);
    mypqueue.emplace(4);
    mypqueue.emplace(5);
    mypqueue.emplace(6);
    // queue becomes 1, 2, 3, 4, 5, 6

    // printing the priority queue
    cout << "mypqueue = ";
    while (!mypqueue.empty()) {
        cout << mypqueue.top() << " ";
        mypqueue.pop();
    }

    return 0;
}
```

**Output:** 

```cpp
mypqueue = 6 5 4 3 2 1
```

## C++

```cpp
// CHARACTER PRIORITY QUEUE
// CPP program to illustrate
// Implementation of emplace() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    priority_queue<char> mypqueue;
    mypqueue.emplace('A');
    mypqueue.emplace('b');
    mypqueue.emplace('C');
    mypqueue.emplace('d');
    mypqueue.emplace('E');
    mypqueue.emplace('f');
    // queue becomes A, b, C, d, E, f

    // printing the priority queue
    cout << "mypqueue = ";
    while (!mypqueue.empty()) {
        cout << mypqueue.top() << " ";
        mypqueue.pop();
    }

    return 0;
}
```

**Output:** 

```cpp
mypqueue = f d b E C A
```

## C++

```cpp
// STRING PRIORITY QUEUE
// CPP program to illustrate
// Implementation of emplace() function
#include <iostream>
#include <queue>
#include <string>
using namespace std;

int main()
{
    priority_queue<string> mypqueue;
    mypqueue.emplace("portal");
    mypqueue.emplace("computer science");
    mypqueue.emplace("is a");
    mypqueue.emplace("GEEKSFORGEEKS");
    // queue becomes portal, computer science,
    // is a, GEEKSFORGEEKS

    // printing the priority queue
    cout << "mypqueue = ";
    while (!mypqueue.empty()) {
        cout << mypqueue.top() << " ";
        mypqueue.pop();
    }

    return 0;
}
```

**Output:** 

```cpp
mypqueue = portal is a computer science GEEKSFORGEEKS
```

**应用:**
给定若干整数，用侵位()将它们加到优先级队列中，求出优先级队列的大小。

```cpp
Input : 5, 13, 0, 9, 4
Output: 5
```

**算法**
1。使用侵位()将给定的元素逐个插入优先级队列容器。
2。不断弹出优先级队列的元素，直到它变成空的，并增加计数器变量。
3。打印计数器变量。

## C++

```cpp
// CPP program to illustrate
// Application of emplace() function
#include <iostream>
#include <queue>
using namespace std;

int main()
{
    int c = 0;

    // Empty Priority Queue
    priority_queue<int> pqueue;

    // inserting elements into priority_queue
    pqueue.emplace(5);
    pqueue.emplace(13);
    pqueue.emplace(0);
    pqueue.emplace(9);
    pqueue.emplace(4);

    // Priority queue becomes 13, 9, 5, 4, 0

    // Counting number of elements in queue
    while (!pqueue.empty()) {
        pqueue.pop();
        c++ ;
    }
    cout << c;
}
```

**Output:** 

```cpp
5
```

**时间复杂度:** O(1)

**侵位()vs push()**
当我们使用 push()时，我们创建一个对象，然后将其插入 priority_queue。使用侵位()，对象就地构造，并保存一个不必要的副本。详见[c++ STL 中的定位与插入](https://www.geeksforgeeks.org/emplace-vs-insert-c-stl/)。

## C++

```cpp
// C++ code to demonstrate difference between
// emplace and insert
#include<bits/stdc++.h>
using namespace std;

int main()
{
    // declaring priority queue
    priority_queue<pair<char, int>> pqueue;

    // using emplace() to insert pair in-place
    pqueue.emplace('a', 24);

    // Below line would not compile
    // pqueue.push('b', 25);   

    // using push() to insert pair
    pqueue.push(make_pair('b', 25));   

    // printing the priority_queue
    while (!pqueue.empty()) {
        pair<char, int> p =  pqueue.top();
        cout << p.first << " "
             << p.second << endl;
        pqueue.pop();
    }

    return 0;
}
```

**Output:** 

```cpp
b 25
a 24
```