# c++ STL 中的 deque::operator=和 deque::operator[]

> 原文:[https://www . geeksforgeeks . org/dequeoperator-dequeoperator-c-STL/](https://www.geeksforgeeks.org/dequeoperator-dequeoperator-c-stl/)

[德客](https://www.geeksforgeeks.org/deque-cpp-stl/)或双端队列是具有两端伸缩特性的序列容器。它们类似于向量，但是在末尾和开头插入和删除元素的情况下效率更高。与向量不同，可能无法保证连续的存储分配。

**deque::operator=**

该运算符用于通过替换现有内容向容器分配新内容。
还会根据新内容修改大小。

**语法:**

```cpp
***dequename1 = (dequename2)***
Parameters :
Another container of the same type.
Result :
Assign the contents of the container passed as 
parameter to the container written on left side of the operator.
```

示例:

```cpp
Input  :  mydeque1 = 1, 2, 3
          mydeque2 = 3, 2, 1, 4
          mydeque1 = mydeque2;
Output :  mydeque1 = 3, 2, 1, 4

Input  :  mydeque1 = 2, 6, 1, 5
          mydeque2 = 3, 2
          mydeque1 = mydeque2;
Output :  mydeque1 = 3, 2
```

**错误和异常**
1。如果容器的类型不同，则会引发错误。
2。否则它有一个基本的无异常抛出保证。

## C++

```cpp
// CPP program to illustrate
// Implementation of = operator
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    deque<int> mydeque1{ 1, 2, 3 };
    deque<int> mydeque2{ 3, 2, 1, 4 };
    mydeque1 = mydeque2;
    cout << "mydeque1 = ";
    for (auto it = mydeque1.begin(); it != mydeque1.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
mydeque1= 3 2 1 4
```

**deque::operator[]**

该运算符用于引用运算符内部给出的*位置*处的元素。它与 at()函数类似，唯一的区别是 at()函数在位置不在 deque 大小的界限内时抛出一个超范围异常，而这个运算符导致**未定义的行为**。

**语法:**

```cpp
***dequename[position]***
Parameters :
Position of the element to be fetched.
Returns :
Direct reference to the element at the given position.
```

示例:

```cpp
Input  :  mydeque = 1, 2, 3
          mydeque[2];
Output :  3

Input  :  mydeque = 3, 4, 1, 7, 3
          mydeque[3];
Output :  7
```

**错误和异常**
1。如果该位置不在 deque 中，它将显示未定义的行为。
2。否则它有一个无异常抛出保证。

## C++

```cpp
// CPP program to illustrate
// Implementation of [] operator
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    deque<int> mydeque;
    mydeque.push_back(3);
    mydeque.push_back(4);
    mydeque.push_back(1);
    mydeque.push_back(7);
    mydeque.push_back(3);
    cout << mydeque[3];
    return 0;
}
```

输出:

```cpp
7
```

**应用程序**
给定一个整数序列，打印偶数位置的所有整数。

```cpp
Input  :1, 2, 3, 4, 5, 6, 7, 8, 9
Output :1 3 5 7 9
*Explanation - 1, 3, 5, 7 and 9 are at position 0, 2, 4, 6 and 8 which are even*
```

**算法**
1。运行一个循环，直到数组的大小。
2。检查该位置是否可被 2 整除，如果是，打印该位置的元素。

## C++

```cpp
// CPP program to illustrate
// Application of [] operator
#include <deque>
#include <iostream>
using namespace std;

int main()
{
    deque<int> mydeque;
    mydeque.push_back(1);
    mydeque.push_back(2);
    mydeque.push_back(3);
    mydeque.push_back(4);
    mydeque.push_back(5);
    mydeque.push_back(6);
    mydeque.push_back(7);
    mydeque.push_back(8);
    mydeque.push_back(9);
    // Deque becomes 1, 2, 3, 4, 5, 6, 7, 8, 9

    for (int i = 0; i < mydeque.size(); ++ i) {
        if (i % 2 == 0) {
            cout << mydeque[i];
            cout << " ";
        }
    }
    return 0;
}
```

输出:

```cpp
1 3 5 7 9
```