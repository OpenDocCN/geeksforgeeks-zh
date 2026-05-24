# 如何用 STL 实现 Min Heap？

> 原文:[https://www.geeksforgeeks.org/implement-min-heap-using-stl/](https://www.geeksforgeeks.org/implement-min-heap-using-stl/)

C++ STL 中有 [priority_queue](https://www.geeksforgeeks.org/priority-queue-container-adaptors-the-c-standard-template-library-stl/) 可以直接用来实现 Max Heap。为了完全理解代码，请确保您熟悉 C++ 中的以下概念

*   [STL 中的容器适配器](http://cs.stmarys.ca/~porter/csc/ref/stl/containers_summary.html)
*   [函子](https://www.geeksforgeeks.org/functors-in-cpp/)

参见以下示例:

## C++

```cpp
// C++ program to show that priority_queue is by
// default a Max Heap
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main ()
{
    // Creates a max heap
    priority_queue <int> pq;
    pq.push(5);
    pq.push(1);
    pq.push(10);
    pq.push(30);
    pq.push(20);

    // One by one extract items from max heap
    while (pq.empty() == false)
    {
        cout << pq.top() << " ";
        pq.pop();
    }

    return 0;
}
```

**Output**

```cpp
30 20 10 5 1 
```

由于元素是按降序打印的，所以默认情况下我们有一个最大堆。

**如何实现闵堆？**
priority_queue 支持一个需要两个额外参数才能使其成为最小堆的构造函数。

```cpp
priority_queue <Type, vector<Type>, ComparisonType > min_heap;
```

`第三个参数，'比较类型'可以是一个函数或因子(又名函数对象)，其返回类型必须为 **bool** ，并且必须有 2 个参数。

下面是一个整数的例子。

## C++

```cpp
// C++ program to use priority_queue to implement min heap
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main ()
{
    // Creates a min heap
    priority_queue <int, vector<int>, greater<int> > pq;
    pq.push(5);
    pq.push(1);
    pq.push(10);
    pq.push(30);
    pq.push(20);

    // One by one extract items from min heap
    while (pq.empty() == false)
    {
        cout << pq.top() << " ";
        pq.pop();
    }

    return 0;
}
```

**输出:**

```cpp
1 5 10 20 30 
```

**使用默认优先级队列进行最小堆的另一种方法:**

这在竞争性编程中经常使用。我们首先用(-1)乘以所有元素。然后我们创建一个最大堆(最大堆是优先级队列的默认值)。当我们访问数据并想要打印它时，我们只需将这些元素再次乘以(-1)。

下面是上述想法的实现:

## C++

```cpp
// C++ Program to implement min heap
// using default priority_queue(max-heap)

#include <iostream>
#include <queue>
using namespace std;

int main()
{
    // data
    int arr[] = { 25, 7, 9, 15, 20, 36, 50 };

      // default priority_queue using max-heap
    priority_queue<int> pq;

      // size of the array
    int n = sizeof(arr) / sizeof(arr[0]);

    // multiply -1 with all elements while
    // inserting
    for (int i = 0; i < n; i++) {
        pq.push((-1) * arr[i]);
    }

    // multiply all elements with -1 while
    // retrieve the elements
    while (!pq.empty()) {
        cout << (pq.top()) * (-1) << " ";
        pq.pop();
    }

    return 0;
}
```

**Output**

```cpp
7 9 15 20 25 36 50 
```

**如何对自定义类进行最小堆？**

让我们考虑下面的例子，其中我们建立了一个由 X 轴排序的二维点的最小堆。

## C++

```cpp
// C++ program to use priority_queue to implement Min Heap
// for user defined class
#include <bits/stdc++.h>
using namespace std;

// User defined class, Point
class Point
{
   int x;
   int y;
public:
   Point(int _x, int _y)
   {
      x = _x;
      y = _y;
   }
   int getX() const { return x; }
   int getY() const { return y; }
};

// To compare two points
class myComparator
{
public:
    int operator() (const Point& p1, const Point& p2)
    {
        return p1.getX() > p2.getX();
    }
};

// Driver code
int main ()
{
    // Creates a Min heap of points (order by x coordinate)
    priority_queue <Point, vector<Point>, myComparator > pq;

    // Insert points into the min heap
    pq.push(Point(10, 2));
    pq.push(Point(2, 1));
    pq.push(Point(1, 5));

    // One by one extract items from min heap
    while (pq.empty() == false)
    {
        Point p = pq.top();
        cout << "(" << p.getX() << ", " << p.getY() << ")";
        cout << endl;
        pq.pop();
    }

    return 0;
}
```

**输出:**

```cpp
(1, 5)
(2, 1)
(10, 2)
```

如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息