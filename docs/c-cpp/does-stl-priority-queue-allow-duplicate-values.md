# STL 优先级队列是否允许重复值？

> 原文:[https://www . geesforgeks . org/do-STL-priority-queue-allow-replicate-values/](https://www.geeksforgeeks.org/does-stl-priority-queue-allow-duplicate-values/)

是的，在 [C++ priority_queue](https://www.geeksforgeeks.org/priority-queue-in-cpp-stl/) 中，我们可能有重复的值。

```cpp
// C++ program to demonstrate that duplicate
// values are allowed in a priority queue
// (with maximum value at the top)
#include <bits/stdc++.h>
using namespace std;

int main()
{
    priority_queue<int> pq;
    pq.push(30);
    pq.push(5);
    pq.push(30);
    cout << pq.top() << " ";
    pq.pop();
    cout << pq.top() << " ";
    pq.pop();
    return 0;
}
```

**Output:**

```cpp
30 30

```

```cpp
// C++ program to demonstrate that duplicate
// values are allowed in a priority queue
// (with minimum value at the top)
#include <bits/stdc++.h>
using namespace std;

int main()
{
    priority_queue<int> pq;
    pq.push(5);
    pq.push(5);
    pq.push(5);
    cout << pq.top() << " ";
    pq.pop();
    cout << pq.top() << " ";
    pq.pop();
    cout << pq.top() << " ";
    pq.pop();
    return 0;
}
```

**Output:**

```cpp
5 5 5

```