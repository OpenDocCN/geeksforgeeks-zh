# c++ STL 中的无序 _ 多集 bucket_count()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-bucket _ count-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-bucket_count-function-in-c-stl/)

**无序 _ 多集::bucket_count()** 是 C++ STL 中的内置函数，返回无序 _ 多集容器中的桶总数。桶是容器内部哈希表中的一个槽，元素根据它们的哈希值被分配给这个槽。

**语法:**

```cpp
unordered_multiset_name.bucket_count()
```

**参数:**函数不接受任何参数。

**返回值:**返回无符号整数类型，表示桶的总数。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multiset::bucket_count() function
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

    cout << "The total count of buckets: " << sample.bucket_count();

    // prints all element bucket wise
    for (int i = 0; i < sample.bucket_count(); i++) {

        cout << "\nBucket " << i << ": ";

        // if bucket is empty
        if (sample.bucket_size(i) == 0)
            cout << "empty";

        for (auto it = sample.cbegin(i); it != sample.cend(i); it++)
            cout << *it << " ";
    }
    return 0;
}
```

**Output:**

```cpp
The total count of buckets: 7
Bucket 0: b b b 
Bucket 1: empty
Bucket 2: empty
Bucket 3: z 
Bucket 4: empty
Bucket 5: empty
Bucket 6: a

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multiset::bucket_count() function
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

    cout << "The total count of buckets: " << sample.bucket_count();

    // prints all element bucket wise
    for (int i = 0; i < sample.bucket_count(); i++) {

        cout << "\nBucket " << i << ": ";

        // if bucket is empty
        if (sample.bucket_size(i) == 0)
            cout << "empty";

        for (auto it = sample.cbegin(i); it != sample.cend(i); it++)
            cout << *it << " ";
    }
    return 0;
}
```

**Output:**

```cpp
The total count of buckets: 7
Bucket 0: b b b 
Bucket 1: empty
Bucket 2: empty
Bucket 3: z 
Bucket 4: empty
Bucket 5: empty
Bucket 6: a

```