# 队列::交换()在 C++ STL 中

> 哎哎哎:# t0]https://www . geeksforgeeks . org/queue-swap-CPP-STL/

[队列](https://www.geeksforgeeks.org/queue-set-1introduction-and-array-implementation/)也是一种抽象数据类型或线性数据结构，它遵循执行操作的特定顺序。顺序是先进先出(**先进先出**)。在先进先出数据结构中，添加到队列中的第一个元素将是第一个被移除的元素。

**队列::swap()**
swap()函数用于交换两个队列的内容，但队列必须是**相同类型的**，尽管大小可能不同。

**语法:**

```cpp
queue1.swap(queue2)
            OR
swap(queue1, queue2)

Parameters:
queue1 is the first queue object.
queue2 is the second queue object.

```

**返回值:**无

**示例:**

```cpp
Input :  queue1 = {1, 2, 3, 4}
         queue2 = {5, 6, 7, 8}
 queue1.swap(queue2);
Output : queue1 = {5, 6, 7, 8}
         queue2 = {1, 2, 3, 4}

Input  : queue1 = {'a', 'b', 'c', 'd', 'e'}
         queue2 = {'f', 'g', 'h', 'i'}
 queue1.swap(queue2);
Output : queue1 = {'f', 'g', 'h', 'i'}
         queue2 = {'a', 'b', 'c', 'd', 'e'}

```

错误和异常

1.如果队列不是同一类型，它将引发错误。
2。否则它有一个基本的无异常抛出保证。

```cpp
// CPP program to illustrate
// Implementation of swap() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Take any two queues
    queue<char> queue1, queue2;
    int v = 96;
    for (int i = 0; i < 5; i++) {
      queue1.push(v + 1);
      v++ ;
    }

   for (int i = 0; i < 4; i++) {
      queue2.push(v + 1);
      v++ ;
    }

    // Swap elements of queues
    queue1.swap(queue2);

    // Print the first queue
    cout << "queue1 = ";
    while (!queue1.empty()) {
      cout << queue1.front() << " ";
      queue1.pop();
   }

    // Print the second set
    cout << endl << "queue2 = ";
    while (!queue2.empty()) {
      cout << queue2.front() << " ";
      queue2.pop();
   }

    return 0;
}
```

输出:

```cpp
queue1 = f g h i 
queue2 = a b c d e 

```

**时间复杂度:**线性即 O(n)