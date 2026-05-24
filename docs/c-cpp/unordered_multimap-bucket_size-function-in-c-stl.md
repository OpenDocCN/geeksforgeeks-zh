# c++ STL 中的无序 _ 多映射 bucket_size()函数

> 原文:[https://www . geesforgeks . org/unordered _ multimap-bucket _ size-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-bucket_size-function-in-c-stl/)

**unordered _ multimap::bucket _ size()**是 C++ STL 中的内置函数，返回 bucket n 中的元素个数。

**语法:**

```cpp
unordered_multimap_name.bucket_size(n)
```

**参数:**该函数接受一个参数 **n** ，该参数指定要返回其计数的桶号。

**返回值:**返回一个无符号整数类型，表示桶号为 n 的桶中的元素数量

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multimap::bucket_size()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<int, int> sample;

    // inserts element
    sample.insert({ 10, 100 });
    sample.insert({ 10, 100 });
    sample.insert({ 20, 200 });
    sample.insert({ 30, 300 });
    sample.insert({ 15, 150 });

    cout << "The total count of buckets: " 
         << sample.bucket_count();

    // prints all element bucket wise
    for (int i = 0; i < sample.bucket_count(); i++) {

        cout << "\nNumber of elements in Bucket " << i
             << " = " << sample.bucket_size(i);
    }
    return 0;
}
```

**Output:**

```cpp
The total count of buckets: 7
Number of elements in Bucket 0 = 0
Number of elements in Bucket 1 = 1
Number of elements in Bucket 2 = 1
Number of elements in Bucket 3 = 2
Number of elements in Bucket 4 = 0
Number of elements in Bucket 5 = 0
Number of elements in Bucket 6 = 1

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multimap::bucket_size() 
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<char, char> sample;

    // inserts element
    sample.insert({ 'a', 'b' });
    sample.insert({ 'a', 'b' });
    sample.insert({ 'b', 'c' });
    sample.insert({ 'r', 'a' });
    sample.insert({ 'c', 'b' });

    cout << "The total count of buckets: " 
         << sample.bucket_count();

    // prints all element bucket wise
    for (int i = 0; i < sample.bucket_count(); i++) {

        cout << "\nNumber of elements in Bucket " << i
             << " = " << sample.bucket_size(i);
    }
    return 0;
}
```

**Output:**

```cpp
The total count of buckets: 7
Number of elements in Bucket 0 = 1
Number of elements in Bucket 1 = 1
Number of elements in Bucket 2 = 1
Number of elements in Bucket 3 = 0
Number of elements in Bucket 4 = 0
Number of elements in Bucket 5 = 0
Number of elements in Bucket 6 = 2

```