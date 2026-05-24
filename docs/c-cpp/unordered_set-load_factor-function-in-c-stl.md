# c++ STL 中的无序 _ 设置加载因子()函数

> 原文:[https://www . geesforgeks . org/unordered _ set-load _ factor-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_set-load_factor-function-in-c-stl/)

**无序 _ 集合::load_factor()** 是 C++ STL 中的内置函数，返回无序 _ 集合容器中的当前加载因子。负载系数是容器中元素的数量(其大小)和桶的数量(bucket_count)之间的比率:

> 负载系数=大小/桶数

负载因子影响哈希表中冲突的概率(即两个元素位于同一个桶中的概率)。容器会自动增加存储桶的数量，以将负载系数保持在特定阈值(其 max_load_factor)以下，方法是在每次需要扩展时进行重新散列。

**语法**:

```cpp
*unordered_set_name*.load_factor()
```

**参数**:函数不接受任何参数。

**返回值**:该函数返回当前负载系数。它可以是整数或双精度类型。

以下程序说明了*无序 _ 设置::加载 _ 因子()*功能:

**程序 1** :

```cpp
// C++ program to illustrate the
// unordered_set::load_factor() function
#include <iostream>
#include <unordered_set>
using namespace std;

int main()
{

    // declaration
    unordered_set<int> sample;

    // inserts element
    sample.insert(1);
    sample.insert(11);
    sample.insert(111);
    sample.insert(12);
    sample.insert(13);

    cout << "The size is: " << sample.size();
    cout << "\nThe bucket_count is: "
         << sample.bucket_count();

    cout << "\nThe load_factor is: "
         << sample.load_factor();

    sample.insert(2);
    sample.insert(22);

    cout << "\n\nThe size is: "
         << sample.size();

    cout << "\nThe bucket_count is: "
         << sample.bucket_count();

    cout << "\nThe load_factor is: "
         << sample.load_factor();

    sample.insert(33);

    cout << "\n\nThe size is: "
         << sample.size();

    cout << "\nThe bucket_count is: "
         << sample.bucket_count();

    cout << "\nThe load_factor is: "
         << sample.load_factor();
    return 0;
}
```

**Output:**

```cpp
The size is: 5
The bucket_count is: 7
The load_factor is: 0.714286

The size is: 7
The bucket_count is: 17
The load_factor is: 0.411765

The size is: 8
The bucket_count is: 17
The load_factor is: 0.470588

```

**程序 2** :

```cpp
// C++ program to illustrate the
// unordered_set::load_factor() function
#include <iostream>
#include <unordered_set>
using namespace std;

int main()
{

    // declaration
    unordered_set<char> sample;

    // inserts element
    sample.insert('a');
    sample.insert('b');
    sample.insert('c');
    sample.insert('r');
    sample.insert('d');

    cout << "The size is: " << sample.size();
    cout << "\nThe bucket_count is: "
         << sample.bucket_count();

    cout << "\nThe load_factor is: "
         << sample.load_factor();

    sample.insert('f');
    sample.insert('k');

    cout << "\n\nThe size is: "
         << sample.size();

    cout << "\nThe bucket_count is: "
         << sample.bucket_count();

    cout << "\nThe load_factor is: "
         << sample.load_factor();

    sample.insert('z');

    cout << "\n\nThe size is: "
         << sample.size();

    cout << "\nThe bucket_count is: "
         << sample.bucket_count();

    cout << "\nThe load_factor is: "
         << sample.load_factor();
    return 0;
}
```

**Output:**

```cpp
The size is: 5
The bucket_count is: 7
The load_factor is: 0.714286

The size is: 7
The bucket_count is: 17
The load_factor is: 0.411765

The size is: 8
The bucket_count is: 17
The load_factor is: 0.470588

```