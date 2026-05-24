# C++ 中元组的优先级队列，示例

> 原文：[https://www.geeksforgeeks.org/priority-queue-of-tuples-in-c-with-examples/](https://www.geeksforgeeks.org/priority-queue-of-tuples-in-c-with-examples/)

`优先队列`

[`优先级队列`](https://www.geeksforgeeks.org/priority-queue-in-cpp-stl/) 是容器适配器的一种类型，专门设计为队列的第一个元素是队列中所有元素中最大的，元素的顺序不递增（因此我们可以看到队列的每个元素都有优先级{固定顺序}）。

与优先级队列相关联的函数：

*   `Empty()`：此函数返回队列是否为空。
*   `size()`：此函数返回队列的大小。
*   `top()`：返回队列顶部元素的引用。
*   `Push(x)`：此函数在队列末尾添加元素 `x`。

`元组`

一个 [`元组`](https://www.geeksforgeeks.org/tuples-in-c/?ref=lbp) 是一个可以容纳多个元素的对象。元素可以是不同的数据类型。元组的元素按照被访问的顺序被初始化为参数。

与元组相关联的函数：

*   `get()`：`get()` 用于访问元组值并修改它们。它接受索引和元组名作为参数来访问特定的元组元素。
*   `make_tuple()`：`make_tuple()` 用于为元组赋值。传递的值应与元组中声明的值类型一致。

本文主要讨论如何在 C++ 中使用元组的优先级队列。元组的优先级队列在设计复杂的数据结构时非常有用。

```cpp
Syntax 1: Max-heap priority queue of tuples:
priority_queue<tuple<data_type1, data_type2, data_type3>> priorityQueue;

Syntax 2: Min-heap priority queue of tuples:
priority_queue<tuple<data_type1, data_type2, data_type3>, 
vector<tuple<data_type1, data_type2, data_type3>>, 
greater<tuple<data_type1, data_type2, data_type3>>> priorityQueue;

Syntax 3: Customized priority queue of tuples (using comparator):
priority_queue<tuple<data_type1, data_type2, data_type3>, 
vector<tuple<data_type1, data_type2, data_type3>>, comparator> priorityQueue;
```

## 元组的最大堆优先级队列

默认情况下，优先级队列是最大堆。因此，在优先级队列中有一对元组的情况下，比较它们的第一个元素，如果两个元组的第一个元素相等，则比较它们的第二个元素，如果第二个元素也相等，则比较第三个元素。具有较大元素的元组成为优先级队列的最顶层元素。

**示例 1：** 下面是实现元组最大堆优先级队列的 C++ 程序。

### C++

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
void print(priority_queue<tuple<int, 
           int, char> > priorityQueue)
{
  while (!priorityQueue.empty()) 
  {
    // Each element of the priority
    // queue is a tuple itself
    tuple<int, int, char> Tuple = 
          priorityQueue.top();

    cout << "[ ";

    cout << get<0>(Tuple) << ' ' << 
            get<1>(Tuple) << ' ' << 
            get<2>(Tuple);
    cout << ']';
    cout << '\n';

    // Pop out the topmost tuple
    priorityQueue.pop();
  }
}

// Driver code
int main()
{
  // Declaring a priority queue of
  // tuple
  priority_queue<tuple<int, int, 
  char> > priorityQueue;

  // Declaring a tuple
  tuple<int, int, char> tuple1;

  // Initializing the tuple
  tuple1 = make_tuple(1, 1, 'G');

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple1);

  // Declaring another tuple
  tuple<int, int, char> tuple2;

  // Initializing the tuple
  tuple2 = make_tuple(2, 2, 'e');

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple2);

  // Declaring another tuple
  tuple<int, int, char> tuple3;

  // Initializing the tuple
  tuple3 = make_tuple(3, 3, 'e');

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple3);

  // Declaring another tuple
  tuple<int, int, char> tuple4;

  // Initializing the tuple
  tuple4 = make_tuple(4, 4, 'k');

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple4);

  // Calling print function
  print(priorityQueue);

  return 0;
}
```

**输出**

```cpp
[ 4 4 k]
[ 3 3 e]
[ 2 2 e]
[ 1 1 G]
```

**示例 2：** 下面是演示元组最大堆优先级队列工作的 C++ 程序。

### C++

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
void print(priority_queue<tuple<int, int, 
           string> > priorityQueue)
{
  while (!priorityQueue.empty()) 
  {
    // Each element of the priority
    // queue is a tuple itself
    tuple<int, int, string> Tuple = 
          priorityQueue.top();

    cout << "[ ";

    cout << get<0>(Tuple) << ' ' << 
            get<1>(Tuple) << ' ' << 
            get<2>(Tuple);
    cout << ']';
    cout << '\n';

    // Pop out the topmost tuple
    priorityQueue.pop();
  }
}

// Driver code
int main()
{
  // Declaring a priority queue
  // of tuple
  priority_queue<tuple<int, int, 
  string> > priorityQueue;

  // Declaring a tuple
  tuple<int, int, string> tuple1;

  // Initializing the tuple
  tuple1 = make_tuple(0, 0, "Geeks");

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple1);

  // Declaring a tuple
  tuple<int, int, string> tuple2;

  // Initializing the tuple
  tuple2 = make_tuple(0, 0, 
                      "Programming");

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple2);

  // Declaring a tuple
  tuple<int, int, string> tuple3;

  // Initializing the tuple
  tuple3 = make_tuple(1, 2, 
                      "Geeks");

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple3);

  // Declaring a tuple
  tuple<int, int, string> tuple4;

  // Initializing the tuple
  tuple4 = make_tuple(1, 3, 
                      "Programming");

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple4);

  // Calling print function
  print(priorityQueue);

  return 0;
}
```

**输出**

```cpp
[ 1 3 Programming]
[ 1 2 Geeks]
[ 0 0 Programming]
[ 0 0 Geeks]
```

## 元组的最小堆优先级队列

对于最小堆优先级队列中的一对元组，比较它们的第一个元素，如果两个元组的第一个元素相等，则比较它们的第二个元素，如果第二个元素也相等，则比较第三个元素。具有较小元素的元组成为优先级队列的最顶层元素。

**示例 1：** 下面是实现元组最小堆优先级队列工作的 C++ 程序。

### C++

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
void print(priority_queue<tuple<int, int, char>,
           vector<tuple<int, int, char> >,
           greater<tuple<int, int, char> > >
           priorityQueue)
{
  while (!priorityQueue.empty()) 
  {
    // Each element of the priority
    // queue is a tuple itself
    tuple<int, int, char> Tuple = 
          priorityQueue.top();

    cout << "[ ";

    cout << get<0>(Tuple) << ' ' << 
            get<1>(Tuple) << ' ' << 
            get<2>(Tuple);
    cout << ']';
    cout << '\n';

    // Pop out the topmost tuple
    priorityQueue.pop();
  }
}

// Driver code
int main()
{
  // Declaring a min-heap priority 
  // queue of tuple
  priority_queue<tuple<int, int, char>,
  vector<tuple<int, int, char> >,
  greater<tuple<int, int, char> > >
          priorityQueue;

  // Declaring a tuple
  tuple<int, int, char> tuple1;

  // Initializing the tuple
  tuple1 = make_tuple(1, 1, 'G');

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple1);

  // Declaring another tuple
  tuple<int, int, char> tuple2;

  // Initializing the tuple
  tuple2 = make_tuple(2, 2, 'e');

  // pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple2);

  // Declaring another tuple
  tuple<int, int, char> tuple3;

  // Initializing the tuple
  tuple3 = make_tuple(3, 3, 'e');

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple3);

  // Declaring another tuple
  tuple<int, int, char> tuple4;

  // Initializing the tuple
  tuple4 = make_tuple(4, 4, 'k');

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple4);

  // Calling print function
  print(priorityQueue);

  return 0;
}
```

**输出**

```cpp
[ 1 1 G]
[ 2 2 e]
[ 3 3 e]
[ 4 4 k]
```

**示例 2：** 下面是实现元组最小堆优先级队列工作的 C++ 程序。

# C++

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
void print(priority_queue<tuple<int, int, string>,
           vector<tuple<int, int, string> >,
           greater<tuple<int, int, string> > >
           priorityQueue)
{
  while (!priorityQueue.empty()) 
  {
    // Each element of the priority
    // queue is a tuple itself
    tuple<int, int, string> Tuple =
          priorityQueue.top();

    cout << "[ ";

    cout << get<0>(Tuple) << ' ' <<
            get<1>(Tuple) << ' ' << 
            get<2>(Tuple);
    cout << ']';
    cout << '\n';

    // Pop out the topmost tuple
    priorityQueue.pop();
  }
}

// Driver code
int main()
{
  // Declaring a priority queue of
  // tuple
  priority_queue<tuple<int, int, string>,
  vector<tuple<int, int, string> >,
  greater<tuple<int, int, string> > >
          priorityQueue;

  // Declaring a tuple
  tuple<int, int, string> tuple1;

  // Initializing the tuple
  tuple1 = make_tuple(0, 0, "Geeks");

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple1);

  // Declaring a tuple
  tuple<int, int, string> tuple2;

  // Initializing the tuple
  tuple2 = make_tuple(0, 0, 
                      "Programming");

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple2);

  // Declaring a tuple
  tuple<int, int, string> tuple3;

  // Initializing the tuple
  tuple3 = make_tuple(1, 2, 
                      "Geeks");

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple3);

  // Declaring a tuple
  tuple<int, int, string> tuple4;

  // Initializing the tuple
  tuple4 = make_tuple(1, 3, 
                      "Programming");

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple4);

  // Calling print function
  print(priorityQueue);

  return 0;
}
```

**输出**

```cpp
[ 0 0 Geeks]
[ 0 0 Programming]
[ 1 2 Geeks]
[ 1 3 Programming]
```

**元组定制优先级队列:**

继续[如何用 STL 实现 Min Heap？](https://www.geeksforgeeks.org/implement-min-heap-using-stl/)是必须的先决条件，我们将在这里学习如何通过将比较器作为参数传递给优先级队列来定制元组的优先级队列。

**例 1:** 下面是实现元组定制优先级队列的 C++ 程序。

## C++ 示例 1

```cpp
// C++ program to implement 
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Comparator
// we can use class also but then 
// we will need to make the function 
// public as class is by default 
// private
struct myComparator 
{
  int operator()(const tuple<int, int, 
                 string>& tuple1,
                 const tuple<int, int, 
                 string>& tuple2)
  {
    // Second element of tuples is equal
    if (get<1>(tuple1) == get<1>(tuple2)) 
    {
      if (get<0>(tuple1) == get<0>(tuple2)) 
      {
        if (get<2>(tuple1) >= get<2>(tuple2))
          return true;
        return false;
      }

      return get<0>(tuple1) >= get<0>(tuple2);
    }

    return get<1>(tuple1) >= get<1>(tuple2);
  }
};

// Function to print priority queue
// contents. Deliberately passing it
// call by value since we don't want
// to remove elements from the priority 
// queue
void print(priority_queue<tuple<int, int, 
           string>,
           vector<tuple<int, int, 
           string> >,
           myComparator>
           priorityQueue)
{
  while (!priorityQueue.empty()) 
  {
    // Each element of the priority
    // queue is a tuple itself
    tuple<int, int, string> Tuple = 
          priorityQueue.top();

    cout << "[ ";

    cout << get<0>(Tuple) << ' ' <<
            get<1>(Tuple) << ' ' << 
            get<2>(Tuple);
    cout << ']';
    cout << '\n';

    // Pop out the topmost tuple
    priorityQueue.pop();
  }
}

// Driver code
int main()
{
  // Declaring a priority queue 
  // of  tuple
  priority_queue<tuple<int, int, string>,
  vector<tuple<int, int, string> >,
  myComparator> priorityQueue;

  // Declaring a tuple
  tuple<int, int, string> tuple1;

  // Initializing the tuple
  tuple1 = make_tuple(0, 0, 
                      "Geeks");

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple1);

  // Declaring a tuple
  tuple<int, int, string> tuple2;

  // Initializing the tuple
  tuple2 = make_tuple(0, 1, 
                      "Programming");

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple2);

  // Declaring a tuple
  tuple<int, int, string> tuple3;

  // Initializing the tuple
  tuple3 = make_tuple(1, 2, 
                      "Geeks");

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple3);

  // Declaring a tuple
  tuple<int, int, string> tuple4;

  // Initializing the tuple
  tuple4 = make_tuple(1, 3, 
                      "Programming");

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple4);

  // Calling print function
  print(priorityQueue);

  return 0;
}
```

**输出**

```cpp
[ 0 0 Geeks]
[ 0 1 Programming]
[ 1 2 Geeks]
[ 1 3 Programming]
```

在上述程序中，对于一对元组，首先比较元组的第二个元素，如果该值相等，则比较第一个元素，如果两个元组的第一个元素相等，则比较第三个元素。否则，具有较小元素的元组将成为最顶端的元素。

**示例 2:** 下面是 C++ 程序，演示元组定制优先级队列的工作。

## c++

```cpp
// C++ program to implement 
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Comparator
// we can use class also but then 
// we will need to make the function
// public as class is by default private
struct myComparator 
{
  int operator()(const tuple<int, int, 
                 string>& tuple1,
                 const tuple<int, int, 
                 string>& tuple2)
  {
    // Second element of tuples is equal
    if (get<1>(tuple1) == get<1>(tuple2)) 
    {
      // first element of tuples is equal
      if (get<0>(tuple1) == get<0>(tuple2)) 
      {
        if (get<2>(tuple1) <= get<2>(tuple2))
          return true;
        return false;
      }

      return get<0>(tuple1) <= get<0>(tuple2);
    }

    return get<1>(tuple1) <= get<1>(tuple2);
  }
};

// Function to print priority queue
// contents. Deliberately passing it
// call by value since we don't want
// to remove elements from the priority 
// queue
void print(priority_queue<tuple<int, int, 
           string>,
           vector<tuple<int, int, string> >,
           myComparator> priorityQueue)
{
  while (!priorityQueue.empty()) 
  {
    // Each element of the priority
    // queue is a tuple itself
    tuple<int, int, string> Tuple = 
          priorityQueue.top();

    cout << "[ ";

    cout << get<0>(Tuple) << ' ' << 
            get<1>(Tuple) << ' ' << 
            get<2>(Tuple);
    cout << ']';
    cout << '\n';

    // Pop out the topmost tuple
    priorityQueue.pop();
  }
}

// Driver code
int main()
{
  // Declaring a priority queue of
  // tuples by passing a custom comparator
  priority_queue<tuple<int, int, string>,
  vector<tuple<int, int, string> >,
  myComparator>
    priorityQueue;

  // Declaring a tuple
  tuple<int, int, string> tuple1;

  // Initializing the tuple
  tuple1 = make_tuple(0, 0, 
                      "Geeks");

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple1);

  // Declaring a tuple
  tuple<int, int, string> tuple2;

  // Initializing the tuple
  tuple2 = make_tuple(0, 1, 
                      "Programming");

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple2);

  // Declaring a tuple
  tuple<int, int, string> tuple3;

  // Initializing the tuple
  tuple3 = make_tuple(1, 2, 
                      "Geeks");

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple3);

  // Declaring a tuple
  tuple<int, int, string> tuple4;

  // Initializing the tuple
  tuple4 = make_tuple(1, 3, 
                      "Programming");

  // Pushing the tuple in the 
  // priority queue
  priorityQueue.push(tuple4);

  // Calling print function
  print(priorityQueue);

  return 0;
}
```

输出

```cpp
[ 1 3 Programming]
[ 1 2 Geeks]
[ 0 1 Programming]
[ 0 0 Geeks]
```

在上述程序中，对于一对元组，首先比较元组的第二个元素，如果该值相等，则比较第一个元素，如果两个元组的第一个元素相等，则比较第三个元素。否则，具有较大元素的元组将成为最顶端的元素。