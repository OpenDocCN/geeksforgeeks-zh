# c++ STL 中的数组::front()和数组::back()

> 原文:[https://www.geeksforgeeks.org/arrayfront-arrayback-c-stl/](https://www.geeksforgeeks.org/arrayfront-arrayback-c-stl/)

[数组](https://www.geeksforgeeks.org/array-class-c/)类一般比 C 风格的数组更高效、轻量、可靠。从 C++ 11 引入数组类为 C 风格的数组提供了一个更好的选择。

**array::front()**

此函数用于引用数组容器的第一个元素。这个函数可以用来获取数组的第一个元素。

**语法:**

```cpp
***arrayname.front()***
Parameters :
No parameters are passed.
Returns :
Direct reference to the first element of the array container.
```

示例:

```cpp
Input :  myarray = {1, 2, 3, 4}
         myarray.front()
Output : 1

Input :  myarray = {3, 6, 2, 8}
         myarray.front()
Output : 3
```

**错误和异常**
1。如果数组容器为空，会导致未定义的行为。
2。如果数组不是空的，它有一个无异常抛出保证。

## C++

```cpp
// CPP program to illustrate
// Implementation of front() function
#include <array>
#include <iostream>
using namespace std;

int main()
{
    array<int, 5> myarray{ 1, 2, 3, 4, 5 };
    cout << myarray.front();
    return 0;
}
```

输出:

```cpp
1
```

**array::back()**

该函数用于引用数组容器的最后一个元素。此函数可用于从数组末尾获取最后一个元素。

**语法:**

```cpp
***arrayname.back()***
Parameters :
No parameters are passed.
Returns :
Direct reference to the last element of the array container.
```

示例:

```cpp
Input :  myarray = {1, 2, 3, 4}
         myarray.back()
Output : 4

Input :  myarray = {4, 5, 6, 7}
         myarray.back()
Output : 7
```

**错误和异常**
1。如果数组容器为空，会导致未定义的行为。
2。如果数组不是空的，它有一个无异常抛出保证。

## C++

```cpp
// CPP program to illustrate
// Implementation of back() function
#include <array>
#include <iostream>
using namespace std;

int main()
{
    array<int, 5> myarray{ 1, 2, 3, 4, 5 };
    cout << myarray.back();
    return 0;
}
```

输出:

```cpp
5
```

**Difference between front(), back() and begin, end() function**

begin()和 end()函数**返回一个迭代器(像指针一样)**初始化为容器的第一个或最后一个元素，可以用来迭代集合，而 front()和 back()函数只是**返回一个引用**到容器的第一个或最后一个元素。

**应用程序**
给定一个整数数组，打印第一个和最后一个元素之间的差。

```cpp
Input: 1, 2, 3, 4, 5, 6, 7, 8
Output:7
Explanation: Last element = 8, First element = 1, Difference = 7
```

**算法**
1。比较第一个和最后一个元素。
2。如果第一个元素较大，减去最后一个元素并打印出来。
3。否则从最后一个元素中减去第一个元素并打印出来。

## C++

```cpp
// CPP program to illustrate
// application Of front() and back() function
#include <array>
#include <iostream>
using namespace std;

int main()
{
    array<int, 8> myarray{ 1, 2, 3, 4, 5, 6, 7, 8 };

    // Array becomes 1, 2, 3, 4, 5, 6, 7, 8

    if (myarray.front() > myarray.back()) {
        cout << myarray.front() - myarray.back();
    }
    else if (myarray.front() < myarray.back()) {
        cout << myarray.back() - myarray.front();
    }
    else
        cout << "0";
}
```

输出:

```cpp
7
```