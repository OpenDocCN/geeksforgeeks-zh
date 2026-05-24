# c++ STL 中的 deque::push_front()

> 哎哎哎::1230【https://www . geeksforgeeks . org/dequepush _ front-c-STL/

或双端队列是具有两端伸缩特性的序列容器。它们类似于向量，但是在末尾和开头插入和删除元素的情况下效率更高。与向量不同，可能无法保证连续的存储分配。

**deque::push_front()**

push_front()函数用于将元素从前面推入队列。在当前第一个元素和容器大小增加 1 之前，新值在开始时插入到 deque 中。

**语法:**

```cpp
*dequename*.push_front(*value*)
Parameters :
The value to be added in the front is 
passed as the parameter
Result :
Adds the value mentioned as the parameter 
to the front of the deque named as dequename

```

示例:

```cpp
Input : deque{1, 2, 3, 4, 5};
        deque.push_front(6);
Output : 6, 1, 2, 3, 4, 5

Input : deque{5, 4, 3, 2, 1};
        deque.push_front(6);
Output :6, 5, 4, 3, 2, 1

```

**错误和异常**

1.强异常保证——如果抛出异常，容器中没有任何变化。
2。如果作为参数传递的值不被 deque 支持，它将显示未定义的行为。

```cpp
// CPP program to illustrate
// push_front() function
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    deque<int> mydeque{ 1, 2, 3, 4, 5 };
    mydeque.push_front(6);

    // deque becomes 6, 1, 2, 3, 4, 5

    for (auto it = mydeque.begin();
         it != mydeque.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
6 1 2 3 4 5
```

**时间复杂度:** O(1)

**应用**
给定一个空的 deque，使用 push_front()函数向其添加整数，然后计算其大小。

```cpp
Input  : 1, 2, 3, 4, 5, 6
Output : 6
```

**算法**
1。使用 push_front()功能
2 向 deque 添加元素。检查 deque 的大小是否为 0，如果不是，则递增初始化为 0 的计数器变量，并弹出前元素。
3。重复此步骤，直到 deque 的大小变为 0。
4。打印变量的最终值。

```cpp
// CPP program to illustrate
// Application of push_front() function
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    int count = 0;
    deque<int> mydeque;
    mydeque.push_front(1);
    mydeque.push_front(2);
    mydeque.push_front(3);
    mydeque.push_front(4);
    mydeque.push_front(5);
    mydeque.push_front(6);
    while (!mydeque.empty()) {
        count++ ;
        mydeque.pop_front();
    }
    cout << count;
    return 0;
}
```

输出:

```cpp
6
```