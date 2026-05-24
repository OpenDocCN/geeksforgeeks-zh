# c++ STL 中的无序 _ 多集保留()

> 原文:[https://www . geesforgeks . org/unordered _ multist-reserve-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-reserve-in-c-stl/)

**无序 _ 多集**的 **reserve()** 功能将容器中的桶数(桶数)设置为最适合包含至少 n 个元素。

如果 n 大于当前存储桶计数乘以 max_load_factor，则容器的存储桶计数会增加，并强制重新散列。

如果 n 低于该值，该函数可能不起作用。

**语法:**

```cpp
void reserve( size_type n );
```

其中 **size_type** 为无符号整型。

**参数:**该方法接受一个强制参数 **n** ，它是作为最小容量请求的元素数量。

**返回:**不返回任何值。

下面是说明 reserve()方法的程序:

**例 1:**

```cpp
#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{
    unordered_multiset<int> j;

    // container invoked
    // it reverse the values
    j.reserve(5);

    // set the values of the container
    j.insert(5);
    j.insert(6);
    j.insert(7);

    cout << "The values in unordered_multiset :";
    for (const int& x : j)
        cout << " " << x;

    return 0;
}
```

**Output:**

```cpp
The values in unordered_multiset : 7 6 5

```

**例 2:**

```cpp
#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{
    unordered_multiset<string> j;

    // container invoked
    // it reverse the values
    j.reserve(5);

    // set the values of the container
    j.insert("Geeks");
    j.insert("forGeeks");
    j.insert("GeeksforGeeks");

    cout << "The values in unordered_multiset :";
    for (const string& x : j)
        cout << " " << x;

    return 0;
}
```

**Output:**

```cpp
The values in unordered_multiset : GeeksforGeeks forGeeks Geeks

```