# c++ STL 中的 vector::operator=和 vector::operator[]

> 原文:[https://www . geeksforgeeks . org/vectoroperator-vectoroperator-c-STL/](https://www.geeksforgeeks.org/vectoroperator-vectoroperator-c-stl/)

[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)与动态数组相同，能够在插入或删除元素时自动调整自身大小，其存储由容器自动处理。

**vector::operator=**

该运算符用于通过替换现有内容向容器分配新内容。
还会根据新内容修改大小。

**语法:**

```cpp
***vectorname1 = (vectorname2)***
Parameters :
Another container of the same type.
Result :
Assign the contents of the container passed as 
parameter to the container written on left side of the operator.
```

示例:

```cpp
Input  :  myvector1 = 1, 2, 3
          myvector2 = 3, 2, 1, 4
          myvector1 = myvector2;
Output :  myvector1 = 3, 2, 1, 4

Input  :  myvector1 = 2, 6, 1, 5
          myvector2 = 3, 2
          myvectoe1 = myvector2;
Output :  myvector1 = 3, 2
```

**错误和异常**
1。如果容器的类型不同，则会引发错误。
2。否则它有一个基本的无异常抛出保证。

## C++

```cpp
// CPP program to illustrate
// Implementation of = operator
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> myvector1{ 1, 2, 3 };
    vector<int> myvector2{ 3, 2, 1, 4 };
    myvector1 = myvector2;
    cout << "myvector1 = ";
    for (auto it = myvector1.begin(); it != myvector1.end(); ++ it)
        cout << ' ' << *it;
    return 0;
}
```

输出:

```cpp
myvector1= 3 2 1 4
```

**vector::operator[]**

该运算符用于引用运算符内部给出的*位置*处的元素。它与 at()函数类似，唯一的区别是 at()函数在位置不在向量大小的界限内时抛出一个超范围异常，而这个运算符导致**未定义的行为**。

**语法:**

```cpp
***vectorname[position]***
Parameters :
Position of the element to be fetched.
Returns :
Direct reference to the element at the given position.
```

示例:

```cpp
Input  :  myvector = 1, 2, 3
          myvector[2];
Output :  3

Input  :  myvector = 3, 4, 1, 7, 3
          myvector[3];
Output :  7
```

**错误和异常**
1。如果该位置不在向量中，它会显示未定义的行为。
2。否则它有一个无异常抛出保证。

## C++

```cpp
// CPP program to illustrate
// Implementation of [] operator
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> myvector;
    myvector.push_back(3);
    myvector.push_back(4);
    myvector.push_back(1);
    myvector.push_back(7);
    myvector.push_back(3);
    cout << myvector[3];
    return 0;
}
```

输出:

```cpp
7
```

**应用**
给定一个整数向量，打印所有出现在奇数位置的整数。

```cpp
Input  :1, 2, 3, 4, 5, 6, 7, 8, 9
Output :2 4 6 8
*Explanation - 2, 4, 6, and 8 are at position 1, 3, 5 and 7 which are odd*
```

**算法**
1。运行一个循环，直到向量的大小。
2。检查该位置是否不能被 2 整除，然后打印该位置的元素。

## C++

```cpp
// CPP program to illustrate
// Application of [] operator
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> myvector;
    myvector.push_back(1);
    myvector.push_back(2);
    myvector.push_back(3);
    myvector.push_back(4);
    myvector.push_back(5);
    myvector.push_back(6);
    myvector.push_back(7);
    myvector.push_back(8);
    myvector.push_back(9);
    // Vector becomes 1, 2, 3, 4, 5, 6, 7, 8, 9

    for (int i = 0; i < myvector.size(); ++ i) {
        if (i % 2 != 0) {
            cout << myvector[i];
            cout << " ";
        }
    }
    return 0;
}
```

输出:

```cpp
2 4 6 8
```