# c++ STL 中的无序 _ 多集桶()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-bucket-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-bucket-function-in-c-stl/)

**无序 _ 多集::bucket()** 是 C++ STL 中的内置函数，返回给定元素所在的 bucket 编号。铲斗大小从 0 到*铲斗 _ 计数-1 不等。*

**语法:**

```cpp
unordered_multiset_name.bucket(element)
```

**参数:**该函数接受单个强制的*元素*，该元素指定要返回其桶号的值。

**返回值:**返回无符号整数类型，表示元素所在的桶号。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multiset::bucket() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<int> sample;

    // inserts element
    sample.insert(10);
    sample.insert(15);
    sample.insert(15);
    sample.insert(13);
    sample.insert(13);

    for (auto it = sample.begin(); it != sample.end(); it++) {
        cout << "The bucket number in which " << *it
             << " is " << sample.bucket(*it) << endl;
    }
    return 0;
}
```

**Output:**

```cpp
The bucket number in which 13 is 6
The bucket number in which 13 is 6
The bucket number in which 10 is 3
The bucket number in which 15 is 1
The bucket number in which 15 is 1

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multiset::bucket() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<char> sample;

    // inserts element
    sample.insert('a');
    sample.insert('a');
    sample.insert('b');
    sample.insert('b');
    sample.insert('c');
    sample.insert('c');
    sample.insert('e');

    for (auto it = sample.begin(); it != sample.end(); it++) {
        cout << "The bucket number in which " << *it
             << " is " << sample.bucket(*it) << endl;
    }
    return 0;
}
```

**Output:**

```cpp
The bucket number in which e is 16
The bucket number in which a is 12
The bucket number in which a is 12
The bucket number in which b is 13
The bucket number in which b is 13
The bucket number in which c is 14
The bucket number in which c is 14

```