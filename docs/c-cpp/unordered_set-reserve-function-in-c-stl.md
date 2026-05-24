# c++ STL 中的无序 _ 集合保留()函数

> 原文:[https://www . geesforgeks . org/unordered _ set-reserve-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-reserve-function-in-c-stl/)

**无序 _ 集合::reserve()** 方法是 C++ STL 中的一个内置函数，用于请求无序 _ 集合的容量变化。它将容器中的桶数设置为至少包含 n 个元素。如果 n 大于当前的**铲斗数量**乘以**最大装载系数**，集装箱的铲斗数量将增加，并强制重新装载。如果 n 小于 bucket_count，则该函数对其没有影响。

**语法**:

```cpp
unordered_set_name.reserve(size_type n)
```

**参数**:该函数接受单个强制参数 *n* ，该参数将容器中的桶数(bucket_count)设置为最适合包含至少 n 个元素。

**返回值**:这个函数不返回任何东西。

下面的程序说明了无序集::保留()函数:

**程序 1:**

```cpp
// C++ program to illustrate
// the unordered_set.reserve()
#include <iostream>
#include <string>
#include <unordered_set>

using namespace std;

int main()
{
    // Declaration of unordered_set
    unordered_set<string> us;

    us.reserve(3);

    us.insert("geeks");
    us.insert("for");
    us.insert("geeks");
    us.insert("users");
    us.insert("geeksforgeeks");

    for (auto it = us.begin(); it != us.end(); it++) {
        cout << *it << " ";
    }

    return 0;
}
```

**Output:**

```cpp
geeksforgeeks users geeks for

```

**程序 2:**

```cpp
// C++ program to illustrate
// the unordered_set.reserve()
#include <iostream>
#include <string>
#include <unordered_set>

using namespace std;

int main()
{
    // Declaration of unordered_set
    unordered_set<string> us;

    us.reserve(0);

    us.insert("geeks");
    us.insert("for");
    us.insert("geeks");

    for (auto it = us.begin(); it != us.end(); it++) {
        cout << *it << " ";
    }

    return 0;
}
```

**Output:**

```cpp
for geeks

```