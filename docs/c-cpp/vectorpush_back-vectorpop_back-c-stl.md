# c++ STL 中的 vector::push_back()和 vector::pop_back()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/vector push _ back-vector pop _ back-c-STL/

[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)与动态数组相同，能够在插入或删除元素时自动调整自身大小，其存储由容器自动处理。

**vector::push_back()**

push_back()函数用于将元素从后面推入向量。新值插入到向量的末尾，在当前最后一个元素之后，容器大小增加 1。

**语法:**

```cpp
***vectorname.push_back(value)***
Parameters :
The value to be added in the back is 
passed as the parameter
Result :
Adds the value mentioned as the parameter 
to the back of the vector named as *vectorname*
```

示例:

```cpp
Input : myvector = {1, 2, 3, 4, 5};
        myvector.push_back(6);
Output :1, 2, 3, 4, 5, 6

Input : myvector = {5, 4, 3, 2, 1};
        myvector.push_back(0);
Output :5, 4, 3, 2, 1, 0
```

**错误和异常**
1。强异常保证——如果抛出异常，容器中没有任何变化。
2。如果向量不支持作为参数传递的值，它将显示未定义的行为。

## C++

```cpp
// CPP program to illustrate
// push_back() function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> myvector{ 1, 2, 3, 4, 5 };
    myvector.push_back(6);

    // Vector becomes 1, 2, 3, 4, 5, 6

    for (auto it = myvector.begin(); it != myvector.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
1 2 3 4 5 6
```

**vector::pop_back()()**

pop_back()函数用于从后面弹出或移除矢量中的元素。该值从向量的末尾移除，容器大小减少 1。

**语法:**

```cpp
***vectorname.pop_back()***
Parameters :
No parameters are passed
Result :
Removes the value present at the end or back 
of the given vector named as *vectorname*
```

示例:

```cpp
Input : myvector = {1, 2, 3, 4, 5};
        myvector.pop_back();
Output :1, 2, 3, 4

Input : myvector = {5, 4, 3, 2, 1};
        myvector.pop_back();
Output :5, 4, 3, 2
```

**错误和异常**
1。不抛出-保证-如果容器不是空的，函数永远不会抛出异常。
2。如果向量为空，它会显示未定义的行为。

## C++

```cpp
// CPP program to illustrate
// pop_back() function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> myvector{ 1, 2, 3, 4, 5 };
    myvector.pop_back();

    // Vector becomes 1, 2, 3, 4

    for (auto it = myvector.begin(); it != myvector.end(); ++ it)
        cout << ' ' << *it;
}
```

输出:

```cpp
1 2 3 4
```

**pop _ back()会移除值和元素吗？**

调用 pop_back()函数时，最后一个元素被移除，*值*和*元素*在这种情况下是一回事。存储对象的析构函数被调用，向量的长度被去除 1。如果容器的容量没有减少，那么您仍然可以访问先前的内存位置，但是在这种情况下，访问已经弹出的元素是没有用的，因为这将导致*未定义的行为*。

**应用** push_back()和 pop_back()
给定一个空向量，使用 push_back 函数向其添加整数，然后计算其大小。

```cpp
Input  : 1, 2, 3, 4, 5, 6
Output : 6
```

**算法**
1。使用 push_back 函数
2 向向量添加元素。检查向量的大小是否为 0，如果不是，则递增初始化为 0 的计数器变量，并弹出 back 元素。
3。重复此步骤，直到向量的大小变为 0。
4。打印变量的最终值。

## C++

```cpp
// CPP program to illustrate
// Application of push_back and pop_back function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    int count = 0;
    vector<int> myvector;
    myvector.push_back(1);
    myvector.push_back(2);
    myvector.push_back(3);
    myvector.push_back(4);
    myvector.push_back(5);
    myvector.push_back(6);
    while (!myvector.empty()) {
        count++ ;
        myvector.pop_back();
    }
    cout << count;
    return 0;
}
```

输出:

```cpp
6
```