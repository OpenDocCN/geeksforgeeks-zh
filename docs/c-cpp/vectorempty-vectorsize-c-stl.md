# c++ STL 中的 vector::empty()和 vector::size()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/vector empty-vector size-c-STL/

[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)与动态数组相同，能够在插入或删除元素时自动调整自身大小，其存储由容器自动处理。

**vector::empty()**

empty()函数用于检查向量容器是否为空。
**语法:**

```cpp
***vectorname***.empty()
Parameters :
No parameters are passed.
Returns :
True, if vector is empty
False, Otherwise
```

**示例:**

```cpp
Input  : myvector = 1, 2, 3, 4, 5
         myvector.empty();
Output : False

Input  : myvector = {}
         myvector.empty();
Output : True
```

**错误和异常**
1。它有一个无异常抛出保证。
2。传递参数时显示错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of empty() function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> myvector{};
    if (myvector.empty())
    {
        cout << "True";
    }
    else {
        cout << "False";
    }
    return 0;
}
```

**Output**

```cpp
True
```

**应用:**
给定一个整数列表，求所有整数的和。

```cpp
Input  : 1, 5, 6, 3, 9, 2
Output : 26
Explanation -  1+5+6+3+9+2 = 26
```

**算法**
1。检查向量是否为空，如果不是，将 back 元素添加到初始化为 0 的变量中，并弹出 back 元素。
2。重复此步骤，直到向量为空。
3。打印变量的最终值。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Application of empty() function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    int sum = 0;
    vector<int> myvector{ 1, 5, 6, 3, 9, 2 };
    while (!myvector.empty())
    {
        sum = sum + myvector.back();
        myvector.pop_back();
    }
    cout << sum;
    return 0;
}
```

**Output**

```cpp
26
```

**vector::size()**

size()函数用于返回向量容器的大小或向量容器中的元素数量。
**语法:**

```cpp
***vectorname***.size()
Parameters :
No parameters are passed.
Returns :
Number of elements in the container.
```

**示例:**

```cpp
Input  : myvector = 1, 2, 3, 4, 5
         myvector.size();
Output : 5

Input  : myvector = {}
         myvector.size();
Output : 0
```

**错误和异常**
1。它有一个无异常抛出保证。
2。传递参数时显示错误。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Implementation of size() function
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> myvector{ 1, 2, 3, 4, 5 };
    cout << myvector.size();
    return 0;
}
```

**Output**

```cpp
5
```