# c++ STL 中的 deque::push_back()

> 哎哎哎::1230【https://www . geeksforgeeks . org/dequepush _ back-c-STL/

去队列或双端队列是序列容器，具有两端扩展和收缩的特性。它们类似于向量，但是在末尾和开头插入和删除元素的情况下效率更高。与向量不同，可能无法保证连续的存储分配。

**deque::push_back()**

push_back()函数用于将元素从后面推入一个队列。新值被插入到当前最后一个元素之前的末尾，容器大小增加 1。
**语法:**

```cpp
***dequename.push_back(value)***
Parameters :
The value to be added in the back is 
passed as the parameter
Result :
Adds the value mentioned as the parameter 
to the back of the deque named as dequename
```

示例:

```cpp
Input : deque{1, 2, 3, 4, 5};
        deque.push_back(6);
Output : 1, 2, 3, 4, 5, 6

Input : deque{5, 4, 3, 2, 1};
        deque.push_back(6);
Output : 5, 4, 3, 2, 1, 6
```

**错误和异常**
1。强异常保证——如果抛出异常，容器中没有任何变化。
2。如果作为参数传递的值不受 deque 的支持，它将显示未定义的行为。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// push_back() function
#include <iostream>
#include <deque>
using namespace std;

int main()
{
    deque<int> mydeque{ 1, 2, 3, 4, 5 };
    mydeque.push_back(6);

    // deque becomes 1, 2, 3, 4, 5, 6

    for (auto it = mydeque.begin();
              it != mydeque.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
1 2 3 4 5 6
```

**时间复杂度:** O(1)
**应用程序**
给定一个空的 deque，使用 push_back()函数向其添加整数，然后计算其所有元素的和。

```cpp
Input  : 11, 2, 5, 3, 7, 1
Output : 29
```

**算法**
1。使用 push_back()函数向 deque 添加元素。
2。检查 deque 的大小是否为 0，如果不是，则将 front 元素添加到初始化为 0 的 sum 变量中，并弹出 front 元素。
3。重复此步骤，直到 deque 的大小变为 0。
4。打印变量的最终值。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Application of push_back() function
#include <iostream>
#include <deque>
using namespace std;

int main()
{
    int sum = 0;
    deque<int> mydeque;
    mydeque.push_back(11);
    mydeque.push_back(2);
    mydeque.push_back(5);
    mydeque.push_back(3);
    mydeque.push_back(7);
    mydeque.push_back(1);
    while (!mydeque.empty()) {
        sum = sum + mydeque.front();
        mydeque.pop_front();
    }
    cout << sum;
    return 0;
}
```

输出:

```cpp
29
```