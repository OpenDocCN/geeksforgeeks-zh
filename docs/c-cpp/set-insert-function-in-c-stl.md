# 在 C++ STL 中设置 insert()函数

> 原文:[https://www.geeksforgeeks.org/set-insert-function-in-c-stl/](https://www.geeksforgeeks.org/set-insert-function-in-c-stl/)

**集合::insert** 是 C++ STL 中的内置函数，它在集合容器中插入元素，或者将集合中一个位置到另一个位置的元素插入到不同的集合中。

*   **语法:**

```cpp
iterator set_name.insert(element)
```

**参数:**该函数接受一个强制参数*元素*，该元素将被插入到集合容器中。
**返回值:**函数返回一个迭代器，指向容器中插入的元素。
**时间复杂度:log(N)** 其中‘N’是集合中的元素个数
下面的程序说明了上面的功能:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to demonstrate the
// set::insert(element) function
#include <bits/stdc++.h>
using namespace std;
int main()
{

    set<int> s;

    // Function to insert elements
    // in the set container
    s.insert(1);
    s.insert(4);
    s.insert(2);
    s.insert(5);
    s.insert(3);

    cout << "The elements in set are: ";
    for (auto it = s.begin(); it != s.end(); it++)
        cout << *it << " ";

    return 0;
}
```

**Output:** 

```cpp
The elements in set are: 1 2 3 4 5
```