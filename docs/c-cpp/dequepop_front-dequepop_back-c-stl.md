# c++ STL 中的 deque::pop_front()和 deque::pop_back()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/dequepop _ front-dequepop _ back-c-STL/

[德客](https://www.geeksforgeeks.org/deque-cpp-stl/)或双端队列是具有两端伸缩特性的序列容器。它们类似于向量，但是在末尾和开头插入和删除元素的情况下效率更高。与向量不同，可能无法保证连续的存储分配。

**deque::pop_front()**

pop_front()函数用于从正面弹出或移除文件中的元素。该值从一开始就从 deque 中移除，并且容器大小减少 1。
**语法:**

```cpp
***dequename.pop_front()***
Parameters :
No value is needed to pass as the parameter.
Result :
Removes the value present at the front 
of the given deque named as *dequename*
```

示例:

```cpp
Input  :  mydeque = 1, 2, 3
          mydeque.pop_front();
Output :  2, 3

Input  :  mydeque = 3, 4, 1, 7, 3
          mydeque.pop_front();
Output :  4, 1, 7, 3
```

**错误和异常**

1.  不抛出-保证-如果抛出异常，容器中没有变化
2.  如果 deque 为空，则显示未定义的行为。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// pop_front() function
#include <iostream>
#include <deque>
using namespace std;

int main()
{
    deque<int> mydeque;
    mydeque.push_front(3);
    mydeque.push_front(2);
    mydeque.push_front(1);
    //Deque becomes 1, 2, 3

    mydeque.pop_front();
    //Deque becomes 2, 3

    for (auto it = mydeque.begin(); it != mydeque.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
2 3
```

**应用:**使用 push_front()功能输入一个空的德格，并打印德格的反面。

```cpp
Input : 1, 2, 3, 4, 5, 6, 7, 8
Output: 8, 7, 6, 5, 4, 3, 2, 1
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// application Of pop_front() function
#include <iostream>
#include <deque>
using namespace std;

int main()
{
    deque<int> mydeque{}, newdeque{};
    mydeque.push_front(8);
    mydeque.push_front(7);
    mydeque.push_front(6);
    mydeque.push_front(5);
    mydeque.push_front(4);
    mydeque.push_front(3);
    mydeque.push_front(2);
    mydeque.push_front(1);

    //Deque becomes 1, 2, 3, 4, 5, 6, 7, 8

    while (!mydeque.empty()) {
        newdeque.push_front(mydeque.front());
        mydeque.pop_front();
    }
    for (auto it = newdeque.begin(); it != newdeque.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
8 7 6 5 4 3 2 1
```

**deque::pop_back()**

pop_back()函数用于从背面弹出或移除文件中的元素。该值从末尾的 deque 中移除，容器大小减少 1。
**语法:**

```cpp
***dequename.pop_back()***
Parameters :
No value is needed to pass as the parameter.
Result :
Removes the value present at the end or back 
of the given deque named as *dequename*
```

示例:

```cpp
Input  :  mydeque = 1, 2, 3
          mydeque.pop_back();
Output :  1, 2

Input  :  mydeque = 3, 4, 1, 7, 3
          mydeque.pop_back();
Output :  3, 4, 1, 7
```

**错误和异常**

1.  不抛出-保证-如果抛出异常，容器中没有变化
2.  如果 deque 为空，则显示未定义的行为。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// pop_back() function
#include <iostream>
#include <deque>
using namespace std;

int main()
{
    deque<int> mydeque;
    mydeque.push_front(5);
    mydeque.push_front(4);
    mydeque.push_front(3);
    mydeque.push_front(2);
    mydeque.push_front(1);
    //Deque becomes 1, 2, 3, 4, 5

    mydeque.pop_back();
    //Deque becomes 1, 2, 3, 4

    for (auto it = mydeque.begin(); it != mydeque.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
1 2 3 4
```

**应用:**
使用 push_front()函数输入一个空的德格，输入以下数字和顺序，打印德格的反面。

```cpp
Input  : 1, 20, 39, 43, 57, 64, 73, 82
Output : 82, 73, 64, 57, 43, 39, 20, 1
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// application Of pop_back() function
#include <iostream>
#include <deque>
using namespace std;

int main()
{
    deque<int> mydeque, newdeque;
    mydeque.push_front(82);
    mydeque.push_front(73);
    mydeque.push_front(64);
    mydeque.push_front(57);
    mydeque.push_front(43);
    mydeque.push_front(39);
    mydeque.push_front(20);
    mydeque.push_front(1);

    //Deque becomes 1, 20, 39, 43, 57, 64, 73, 82

    while (!mydeque.empty()) {
        newdeque.push_back(mydeque.back());
        mydeque.pop_back();
    }
    for (auto it = newdeque.begin(); it != newdeque.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
82 73 64 57 43 39 20 1
```