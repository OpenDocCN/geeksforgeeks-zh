# c++ STL 中的 multimap equal_range()

> 原文:[https://www . geesforgeks . org/multimap-equal _ range-in-c-STL/](https://www.geeksforgeeks.org/multimap-equal_range-in-c-stl/)

**multimap::equal_range()** 是 C++ STL 中的一个内置函数，它返回一个对的迭代器。该对指的是一个范围的边界，该范围包括容器中所有键等价于 K 的元素。如果与键 K 不匹配，则返回的范围长度为 0，两个迭代器都指向第一个元素，根据容器的内部比较对象(key_comp)，该元素的键被认为在 K 之后。

**语法:**

```cpp
iterator multimap_name.equal_range(key)

```

**参数:**该函数接受单个强制参数*键*，该键指定容器中要返回其范围的元素。

**返回值:**函数返回一个对的迭代器。该对指的是一个范围的边界，该范围包括容器中所有键等价于 K 的元素。如果与键 K 不匹配，则返回的范围长度为 0，两个迭代器都指向第一个元素，根据容器的内部比较对象(key_comp)，该元素的键被认为在 K 之后。

程序下面举例说明以上方法:

## c++

```cpp
// C++ program to illustrate the
// multimap::equal_range() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    multimap<int, int> mp;
    // insert elements in random order
    mp.insert({ 2, 30 });
    mp.insert({ 1, 40 });
    mp.insert({ 3, 60 });
    mp.insert({ 1, 20 });
    mp.insert({ 5, 50 });

    // Stores the range of key 1
    auto it = mp.equal_range(1);

    cout << "The multimap elements of key 1 is : \n";
    cout << "KEY\tELEMENT\n";

    // Prints all the elements of key 1
    for (auto itr = it.first; itr != it.second; ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }
    return 0;
}
```

**输出:**

```cpp
The multimap elements of key 1 is : 
KEY    ELEMENT
1    40
1    20

```