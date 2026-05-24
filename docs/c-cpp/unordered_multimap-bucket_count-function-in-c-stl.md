# c++ STL 中的无序 _ 多 map bucket_count()函数

> 原文:[https://www . geesforgeks . org/unordered _ multimap-bucket _ count-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-bucket_count-function-in-c-stl/)

**无序 _ 多 map::bucket_count()** 是 C++ STL 中的内置函数，返回无序 _ 多 map 容器中的桶总数。桶是容器内部哈希表中的一个槽，元素根据它们的哈希值被分配给这个槽。

**语法:**

```cpp
*unordered_multimap_name*.bucket_count()
```

**参数:**函数不接受任何参数。

**返回值:**返回无符号整数类型，表示桶的总数。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multimap::bucket_count() 
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<int, int> sample;

    // inserts key and element
    sample.insert({ 10, 100 });
    sample.insert({ 10, 100 });
    sample.insert({ 20, 200 });
    sample.insert({ 30, 300 });
    sample.insert({ 15, 150 });

    cout << "The total count of buckets: " 
         << sample.bucket_count();

    // prints all element bucket wise
    for (int i = 0; i < sample.bucket_count(); i++) {

        cout << "\nBucket " << i << ": ";

        // if bucket is empty
        if (sample.bucket_size(i) == 0)
            cout << "empty";

        for (auto it = sample.cbegin(i); 
                  it != sample.cend(i); it++)
            cout << "{" << it->first << ", " 
                 << it->second << "}, ";
    }
    return 0;
}
```

**Output:**

```cpp
The total count of buckets: 7
Bucket 0: empty
Bucket 1: {15, 150}, 
Bucket 2: {30, 300}, 
Bucket 3: {10, 100}, {10, 100}, 
Bucket 4: empty
Bucket 5: empty
Bucket 6: {20, 200},

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multimap::bucket_count() 
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<char, char> sample;

    // inserts key and element
    sample.insert({ 'a', 'b' });
    sample.insert({ 'a', 'b' });
    sample.insert({ 'b', 'c' });
    sample.insert({ 'r', 'a' });
    sample.insert({ 'c', 'b' });

    cout << "The total count of buckets: " 
         << sample.bucket_count();

    // prints all element bucket wise
    for (int i = 0; i < sample.bucket_count(); i++) {

        cout << "\nBucket " << i << ": ";

        // if bucket is empty
        if (sample.bucket_size(i) == 0)
            cout << "empty";

        for (auto it = sample.cbegin(i); 
                    it != sample.cend(i); it++)
            cout << "{" << it->first << ", " 
                 << it->second << "}, ";
    }
    return 0;
}
```

**Output:**

```cpp
The total count of buckets: 7
Bucket 0: {b, c}, 
Bucket 1: {c, b}, 
Bucket 2: {r, a}, 
Bucket 3: empty
Bucket 4: empty
Bucket 5: empty
Bucket 6: {a, b}, {a, b},

```