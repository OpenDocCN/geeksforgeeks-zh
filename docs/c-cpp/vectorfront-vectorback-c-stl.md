# c++ STL 中的 vector::front()和 vector::back()

> 原文:[https://www.geeksforgeeks.org/vectorfront-vectorback-c-stl/](https://www.geeksforgeeks.org/vectorfront-vectorback-c-stl/)

[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)与动态数组相同，能够在插入或删除元素时自动调整自身大小，其存储由容器自动处理。

**vector::front()**

这个函数可以用来获取向量容器的第一个元素。
**语法:**

```cpp
***vectorname.front()***
Parameters :
No value is needed to pass as the parameter.
Returns :
Direct reference to the first element of the vector container.
```

示例:

```cpp
Input  :  myvector = 1, 2, 3
          myvector.front();
Output :  1

Input  :  myvector = 3, 4, 1, 7, 3
          myvector.front();
Output :  3
```

**错误和异常**
1。如果向量容器是空的，它会导致未定义的行为。
2。如果向量不是空的，它有一个无异常抛出保证。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of front() function
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
    // Vector becomes 3, 4, 1, 7, 3

    cout << myvector.front();
    return 0;
}
```

输出:

```cpp
3
```

**vector::back()**

这个函数可以用来获取向量容器的最后一个元素。
**语法:**

```cpp
***vectorname.back()***
Parameters :
No value is needed to pass as the parameter.
Returns :
Direct reference to the last element of the vector container.
```

示例:

```cpp
Input  :  myvector = 1, 2, 3
          myvector.back();
Output :  3

Input  :  myvector = 3, 4, 1, 7, 2
          myvector.back();
Output :  2
```

**错误和异常**
1。如果向量容器是空的，它会导致未定义的行为。
2。如果向量不是空的，它有一个无异常抛出保证。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of back() function
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
    myvector.push_back(2);
    // Vector becomes 3, 4, 1, 7, 2

    cout << myvector.back();
    return 0;
}
```

输出:

```cpp
2
```

**前()、后()和开始、结束()功能的区别**

begin()和 end()函数**返回一个迭代器(像指针一样)**初始化为容器的第一个或最后一个元素，可以用来迭代集合，而 front()和 back()函数只是**返回一个引用**到容器的第一个或最后一个元素。
**应用:**给定一个整数的空向量，给向量加上数字，然后打印第一个和最后一个元素的差。

```cpp
Input  : 1, 2, 3, 4, 5, 6, 7, 8
Output : 7
Explanation - Last element = 8, First element = 1, Difference = 7
```

**算法**
1。使用 push_back()函数
2 向向量添加数字。比较第一个和最后一个元素。
3。如果第一个元素较大，减去最后一个元素并打印出来。
4。否则从最后一个元素中减去第一个元素并打印出来。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// application Of front() and back() function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> myvector;
    myvector.push_back(8);
    myvector.push_back(7);
    myvector.push_back(6);
    myvector.push_back(5);
    myvector.push_back(4);
    myvector.push_back(3);
    myvector.push_back(2);
    myvector.push_back(1);

    // Vector becomes 1, 2, 3, 4, 5, 6, 7, 8

    if (myvector.front() > myvector.back()) {
        cout << myvector.front() - myvector.back();
    }
    else if (myvector.front() < myvector.back()) {
        cout << myvector.back() - myvector.front();
    }
    else
        cout << "0";
}
```

输出:

```cpp
7
```