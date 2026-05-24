# c++ STL 中的无序 _ 多集 load_factor()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-load _ factor-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-load_factor-function-in-c-stl/)

**无序 _ 多集::load_factor()** 是 C++ STL 中的内置函数，返回返回无序 _ 多集容器中的当前加载因子。负载系数是容器中元素的数量(其大小)和桶的数量(bucket_count)之间的比率:

> 负载系数=大小/桶数

负载因子影响哈希表中冲突的概率(即两个元素位于同一个桶中的概率)。容器会自动增加存储桶的数量，以将负载系数保持在特定阈值(其 max_load_factor)以下，方法是在每次需要扩展时进行重新散列。

**语法**:

```cpp
*unordered_multiset_name*.load_factor
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回当前负载系数。它可以是整数或双精度类型。

以下程序说明了*无序 _ 多集::加载 _ 因子()*功能:

**程序 1** :

```cpp
// C++ program to illustrate the
// unordered_multiset::load_factor() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<char> sample;

    // inserts element
    sample.insert('a');
    sample.insert('b');

    cout << "The size is: " << sample.size();
    cout << "\nThe bucket_count is: " << sample.bucket_count();
    cout << "\nThe load_factor is: " << sample.load_factor();

    sample.insert('b');
    sample.insert('b');

    cout << "\n\nThe size is: " << sample.size();
    cout << "\nThe bucket_count is: " << sample.bucket_count();
    cout << "\nThe load_factor is: " << sample.load_factor();

    sample.insert('z');

    cout << "\n\nThe size is: " << sample.size();
    cout << "\nThe bucket_count is: " << sample.bucket_count();
    cout << "\nThe load_factor is: " << sample.load_factor();

    return 0;
}
```

**Output:**

```cpp
The size is: 2
The bucket_count is: 3
The load_factor is: 0.666667

The size is: 4
The bucket_count is: 7
The load_factor is: 0.571429

The size is: 5
The bucket_count is: 7
The load_factor is: 0.714286

```

**程序 2** :

```cpp
// C++ program to illustrate the
// unordered_multiset::load_factor() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multiset<int> sample;

    // inserts element
    sample.insert(1);
    sample.insert(1);

    cout << "The size is: " << sample.size();
    cout << "\nThe bucket_count is: " << sample.bucket_count();
    cout << "\nThe load_factor is: " << sample.load_factor();

    sample.insert(1);
    sample.insert(2);

    cout << "\n\nThe size is: " << sample.size();
    cout << "\nThe bucket_count is: " << sample.bucket_count();
    cout << "\nThe load_factor is: " << sample.load_factor();

    sample.insert(2);

    cout << "\n\nThe size is: " << sample.size();
    cout << "\nThe bucket_count is: " << sample.bucket_count();
    cout << "\nThe load_factor is: " << sample.load_factor();

    return 0;
}
```

**Output:**

```cpp
The size is: 2
The bucket_count is: 3
The load_factor is: 0.666667

The size is: 4
The bucket_count is: 7
The load_factor is: 0.571429

The size is: 5
The bucket_count is: 7
The load_factor is: 0.714286

```