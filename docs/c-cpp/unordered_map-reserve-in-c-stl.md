# c++ STL 中的无序 _ 地图储备()

> 原文:[https://www . geesforgeks . org/unordered _ map-reserve-in-c-STL/](https://www.geeksforgeeks.org/unordered_map-reserve-in-c-stl/)

正如我们所知，Bucket 是容器内部哈希表中的一个槽，所有元素都是根据它们的键的哈希值分配给它的。桶的编号从 0 到桶计数。现在作为一个桶持有可变数量的项目。该数字基于术语**负载系数**。当**装载因子(load_factor)** 达到某个阈值时，容器会增加铲斗数量并重新提升地图。但是当我们调用**重新散列(n)** 时，它直接将桶的数量设置为 n，并触发整个哈希表的重建。但是当我们调用 **reserve(n)** 时，它会创建足够的 Buckets 来保存至少 n 个项目。如果我们将> n 个项目添加到地图中，根据负载系数，可能会触发一次重挂。通过为无序的 map 容器调用我们期望的大小的 reserve，我们避免了容器大小的增加可能产生的多次重散列，并优化了哈希表的大小。C++ 函数 std::unordered_map::reserve()将容器中的桶数(bucket_count)设置为最适合包含至少 n 个元素的值。

**语法:**

```cpp
*unordered_map_name*.reserve(N)
```

**参数:**该函数接受单个强制参数 ***N*** ，该参数将请求的元素数量指定为最小容量。

**返回值:**函数不返回任何内容。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_map::reserve()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_map<int, int> sample1, sample2;

    // the sample1 size is reserved for
    // the bucket to contain a minimum of
    // one elements
    sample1.reserve(1);

    // inserts key and element
    // in sample1
    sample1.insert({ 10, 100 });
    sample1.insert({ 50, 500 });

    // inserts key and element
    // in sample1

    // the sample1 size is reserved for
    // the bucket to contain a minimum of
    // three elements
    sample2.reserve(3);

    sample2.insert({ 20, 200 });
    sample2.insert({ 30, 300 });
    sample2.insert({ 30, 150 });

    cout << "The size of Sample1 is: " << sample1.size();

    cout << "\nKey and Elements of Sample1 are:";
    for (auto it = sample1.begin(); it != sample1.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    cout << "\n\nThe size of Sample2 is: " << sample2.size();

    cout << "\nKey and Elements of Sample2 are:";
    for (auto it = sample2.begin(); it != sample2.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    return 0;
}
```

**Output:**

```cpp
The size of Sample1 is: 2
Key and Elements of Sample1 are:{50, 500} {10, 100} 

The size of Sample2 is: 2
Key and Elements of Sample2 are:{30, 300} {20, 200}

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_map::reserve()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_map<char, char> sample1, sample2;

    // the sample1 size is reserved for
    // the bucket to contain a minimum of
    // one elements
    sample1.reserve(1);

    // inserts key and element
    // in sample1
    sample1.insert({ 'a', 'A' });
    sample1.insert({ 'g', 'G' });

    // inserts key and element
    // in sample1

    // the sample1 size is reserved for
    // the bucket to contain a minimum of
    // three elements
    sample2.reserve(3);

    sample2.insert({ 'b', 'B' });
    sample2.insert({ 'c', 'C' });
    sample2.insert({ 'd', 'D' });

    cout << "The size of Sample1 is: " << sample1.size();

    cout << "\nKey and Elements of Sample1 are:";
    for (auto it = sample1.begin(); it != sample1.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    cout << "\n\nThe size of Sample2 is: " << sample2.size();

    cout << "\nKey and Elements of Sample2 are:";
    for (auto it = sample2.begin(); it != sample2.end(); it++) {
        cout << "{" << it->first << ", " << it->second << "} ";
    }

    return 0;
}
```

**Output:**

```cpp
The size of Sample1 is: 2
Key and Elements of Sample1 are:{g, G} {a, A} 

The size of Sample2 is: 3
Key and Elements of Sample2 are:{d, D} {c, C} {b, B}

```