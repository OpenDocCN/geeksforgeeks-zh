# c++ STL 中的无序 _ 多集 bucket_size()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-bucket _ size-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-bucket_size-function-in-c-stl/)

**无序 _ 多集::存储桶 _ 大小()**是 C++ STL 中的内置函数，它返回存储桶中具有元素*值*的元素数量。它将始终低于桶计数。存储桶中元素的数量会影响访问存储桶中特定元素所需的时间

**语法:**

```cpp
unordered_multiset_name.bucket_size(val)
```

**参数:**该函数接受一个参数**值**，该参数指定要返回的桶大小的元素。

**返回值:**它返回一个无符号整数类型，表示具有元素*值*的桶中的元素数量。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multiset::bucket_size() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<int> sample;

    // inserts element
    sample.insert(11);
    sample.insert(11);
    sample.insert(11);
    sample.insert(12);
    sample.insert(13);
    sample.insert(13);
    sample.insert(14);

    for (auto it = sample.begin(); it != sample.end(); it++) {
        cout << "The bucket size in which " << *it
             << " is " << sample.bucket_size(*it) << endl;
    }
    return 0;
}
```

**Output:**

```cpp
The bucket size in which 14 is 1
The bucket size in which 11 is 3
The bucket size in which 11 is 3
The bucket size in which 11 is 3
The bucket size in which 12 is 1
The bucket size in which 13 is 2
The bucket size in which 13 is 2

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multiset::bucket_size() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<int> sample;

    // inserts element
    sample.insert(1);
    sample.insert(1);
    sample.insert(1);
    sample.insert(2);
    sample.insert(3);
    sample.insert(4);
    sample.insert(3);

    for (auto it = sample.begin(); it != sample.end(); it++) {
        cout << "The bucket size in which " << *it
             << " is " << sample.bucket_size(*it) << endl;
    }
    return 0;
}
```

**Output:**

```cpp
The bucket size in which 1 is 3
The bucket size in which 1 is 3
The bucket size in which 1 is 3
The bucket size in which 2 is 1
The bucket size in which 3 is 2
The bucket size in which 3 is 2
The bucket size in which 4 is 1

```