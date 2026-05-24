# c++ STL 中的无序 _ 映射加载 _ 因子

> 原文:[https://www . geesforgeks . org/unordered _ map-load _ factor-in-c-STL/](https://www.geeksforgeeks.org/unordered_map-load_factor-in-c-stl/)

无序映射::load_factor()是 C++ STL 中的内置函数，它返回无序映射容器中的当前加载因子。加载因子是容器中元素的数量(其大小)与桶的数量(桶计数)之间的比率:
**加载因子=大小/桶计数**
加载因子影响哈希表中冲突的概率(即两个元素位于同一个桶中的概率)。容器会自动增加存储桶的数量，以将负载系数保持在特定阈值(其 max_load_factor)以下，方法是在每次需要扩展时进行重新散列。

**语法:**

```cpp
unordered_map_name.load_factor()
```

**参数:**函数不接受任何参数。

**返回值:**该函数返回当前负载系数。

**示例-1:**

```cpp
// C++ program to illustrate the
// unordered_map::load_factor() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration of unordered_map
    unordered_map<int, int> sample;

    // inserts element
    sample.insert({ 1, 2 });
    sample.insert({ 2, 4 });
    sample.insert({ 5, 8 });
    sample.insert({ 7, 10 });

    cout << "The size is: " << sample.size();
    cout << "\nThe bucket_count is: "
         << sample.bucket_count();

    cout << "\nThe load_factor is: "
         << sample.load_factor();

    sample.insert({ 9, 0 });

    cout << "\n\nThe size is: "
         << sample.size();

    cout << "\nThe bucket_count is: "
         << sample.bucket_count();

    cout << "\nThe load_factor is: "
         << sample.load_factor();

    sample.insert({ 11, 1 });

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
The size is: 4
The bucket_count is: 7
The load_factor is: 0.571429

The size is: 5
The bucket_count is: 7
The load_factor is: 0.714286

The size is: 6
The bucket_count is: 7
The load_factor is: 0.857143

```

**示例-2:**

```cpp
// C++ program to illustrate the
// unordered_map::load_factor() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration of unordered_map
    unordered_map<char, int> sample;

    // inserts element
    sample.insert({ 'a', 2 });
    sample.insert({ 'b', 4 });
    sample.insert({ 'c', 8 });
    sample.insert({ 'd', 10 });

    cout << "The size is: " << sample.size();
    cout << "\nThe bucket_count is: "
         << sample.bucket_count();

    cout << "\nThe load_factor is: "
         << sample.load_factor();

    sample.insert({ 'e', 0 });
    sample.insert({ 'h', 5 });

    cout << "\n\nThe size is: "
         << sample.size();

    cout << "\nThe bucket_count is: "
         << sample.bucket_count();

    cout << "\nThe load_factor is: "
         << sample.load_factor();

    sample.insert({ 'f', 1 });

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
The size is: 4
The bucket_count is: 7
The load_factor is: 0.571429

The size is: 6
The bucket_count is: 7
The load_factor is: 0.857143

The size is: 7
The bucket_count is: 17
The load_factor is: 0.411765

```