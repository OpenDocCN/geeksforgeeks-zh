# c++ STL 中的无序 _ 多集 cend()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-cend-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-cend-function-in-c-stl/)

**无序 _ 多集::cend()** 是 C++ STL 中的一个内置函数，它返回一个常量迭代器，指向容器中最后一个元素紧接着的位置，或者指向它的一个桶中最后一个元素紧接着的位置。

**语法:**

```cpp
unordered_multiset_name.cend(n)
```

**参数:**函数接受一个参数。如果传递了一个参数，它会返回一个常量迭代器，指向桶中最后一个元素之后的位置。如果没有传递参数，那么它会返回一个常量迭代器，指向无序多集容器中最后一个元素之后的位置。

**返回值:**返回常量迭代器。它不能用于修改容器的内容。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multiset::cend() function
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

    cout << "\nElements: ";

    // prints all element till the last
    for (auto it = sample.cbegin(); it != sample.cend(); it++)
        cout << *it << " ";
    return 0;
}
```

**Output:**

```cpp
Elements: 13 13 10 15 15

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multiset::cend() function
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

    cout << "\nElements: ";

    // prints all element
    for (auto it = sample.cbegin(); it != sample.cend(); it++)
        cout << *it << " ";
    return 0;
}
```

**Output:**

```cpp
Elements: z a b b b

```

**程序 3:**

```cpp
// C++ program to illustrate the
// unordered_multiset::cend() function
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

    // prints all element bucket wise

    for (int i = 0; i < sample.bucket_count(); i++) {

        cout << "Bucket " << i << ": ";

        // if bucket is empty
        if (sample.bucket_size(i) == 0)
            cout << "empty";

        for (auto it = sample.cbegin(i); it != sample.cend(i); it++)
            cout << *it << " ";

        cout << endl;
    }
    return 0;
}
```

**Output:**

```cpp
Bucket 0: b b b 
Bucket 1: empty
Bucket 2: empty
Bucket 3: z 
Bucket 4: empty
Bucket 5: empty
Bucket 6: a

```