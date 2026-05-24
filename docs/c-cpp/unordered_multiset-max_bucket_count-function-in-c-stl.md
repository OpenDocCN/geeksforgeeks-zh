# c++ STL 中的无序 _ 多集 max_bucket_count()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-max _ bucket _ count-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-max_bucket_count-function-in-c-stl/)

**无序多集::max_bucket_count()** 是 C++ STL 中的内置函数，返回无序多集容器可以拥有的最大桶数。这是它所能拥有的最大值，尽管有碰撞，但由于某些限制，它不能超过。

**语法**:

```cpp
*unordered_multiset_name*.max_bucket_count()
```

**参数**:功能不接受任何东西。

**返回值**:该函数返回可能的最大桶数。

以下程序说明了*无序 _ 多集::最大 _ 桶 _ 计数()*功能:

**程序 1** :

```cpp
// C++ program to illustrate the
// unordered_multiset::maximum_bucket_count() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<char> sample;

    // inserts element
    sample.insert('a');
    sample.insert('b');
    sample.insert('b');
    sample.insert('b');
    sample.insert('z');

    cout << "The maximum bucket count is: " << 
                      sample.max_bucket_count();

    return 0;
}
```

**Output:**

```cpp
The maximum bucket count is: 1152921504606846975

```

**程序 2** :

```cpp
// C++ program to illustrate the
// unordered_multiset::maximum_bucket_count() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<int> sample;

    // inserts element
    sample.insert(1);
    sample.insert(2);
    sample.insert(2);
    sample.insert(4);
    sample.insert(4);

    cout << "The maximum bucket count is: " 
                << sample.max_bucket_count();

    return 0;
}
```

**Output:**

```cpp
The maximum bucket count is: 1152921504606846975

```