# c++ STL 中的无序 _ 映射 max _ bucket _ count

> 原文:[https://www . geesforgeks . org/unordered _ map-max _ bucket _ count-in-c-STL/](https://www.geeksforgeeks.org/unordered_map-max_bucket_count-in-c-stl/)

**无序 _ 映射::max_bucket_count** 是 C++ STL 中的内置函数。它返回无序映射容器可以拥有的最大桶数。

**语法**

```cpp
unordered_map.max_bucket_count()
```

**参数:**不接受任何参数。

**返回类型:**返回最大桶数。返回类型是无符号整数。

**示例-1:**

```cpp
// C++ program to illustrate the
// unordered_map::max_bucket_count function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration of unordered_map
    unordered_map<int, int> sample;

    cout << "Size is : " << sample.size() << endl;
    cout << "Max bucket count is : " << sample.max_bucket_count() << endl;

    // insert elements
    sample.insert({ 5, 10 });
    sample.insert({ 10, 10 });
    sample.insert({ 15, 10 });
    sample.insert({ 20, 10 });
    sample.insert({ 21, 10 });

    cout << "Size is : " << sample.size() << endl;
    cout << "Max bucket count is : " << sample.max_bucket_count() << endl;
    return 0;
}
```

**输出:**

```cpp
Size is : 0
Max bucket count is : 1152921504606846975
Size is : 5
Max bucket count is : 1152921504606846975

```

**示例-2:**

```cpp
// C++ program to illustrate the
// unordered_map::max_bucket_count function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration of unordered_map
    unordered_map<char, int> sample;

    cout << "Size is : " << sample.size() << endl;
    cout << "Max bucket count is : " << sample.max_bucket_count() << endl;

    // insert elements
    sample.insert({ 'a', 10 });
    sample.insert({ 'b', 10 });
    sample.insert({ 'c', 10 });
    sample.insert({ 'd', 10 });
    sample.insert({ 'e', 10 });
    sample.insert({ 'f', 10 });

    cout << "Size is : " << sample.size() << endl;
    cout << "Max bucket count is : " << sample.max_bucket_count() << endl;
    return 0;
}
```

**输出:**

```cpp
Size is : 0
Max bucket count is : 1152921504606846975
Size is : 6
Max bucket count is : 1152921504606846975

```

**复杂度:**其复杂度不变。