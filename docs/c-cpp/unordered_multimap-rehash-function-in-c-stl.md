# c++ STL 中无序 _ 多映射重散列()函数

> 原文:[https://www . geesforgeks . org/unordered _ multimap-rehash-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-rehash-function-in-c-stl/)

**unordered _ multimap::rehash(N)**是 C++ STL 中的内置函数，它将容器中的桶数设置为 N 或更多。如果 N 大于容器中当前的桶数(桶数)，则强制*重新散列*。
新的桶数可以等于或大于 n。如果 n 小于容器中当前的桶数([桶数](https://www.geeksforgeeks.org/unordered_multimap-bucket_count-function-in-c-stl/)，该功能可能对桶数没有影响，并且可能不会强制重新散列。
重新散列是哈希表的重建:容器中的所有元素根据它们的哈希值重新排列成新的桶集。这可能会改变容器内元素的迭代顺序，尽管保留了具有等效键的元素的相对顺序。每当容器的[负载系数](https://www.geeksforgeeks.org/unordered_multimap-load_factor-function-in-c-stl/)在一次操作中将要超过其最大负载系数时，容器会自动执行重新装载。通过调用 rehash 在哈希表中保留一定数量的最小桶，我们避免了容器扩展可能导致的多次重散列。

**语法:**

```cpp
*unordered_multimap_name*.rehash(N)
```

**参数:**该函数接受单个强制参数 ***N*** ，该参数指定容器哈希表的最小桶数。

**返回值:**函数不返回任何内容。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multimap::rehash()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<int, int> sample1, sample2;

    // the sample1 size is reserved for
    // the bucket to contain a minimum of
    // one elements
    sample1.rehash(1);

    // inserts key and element
    // in sample1
    sample1.insert({ 10, 100 });
    sample1.insert({ 50, 500 });

    // inserts key and element
    // in sample1

    // the sample1 size is reserved for
    // the bucket to contain a minimum of
    // three elements
    sample2.rehash(3);

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

The size of Sample2 is: 3
Key and Elements of Sample2 are:{30, 150} {30, 300} {20, 200}

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multimap::rehash()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<char, char> sample1, sample2;

    // the sample1 size is reserved for
    // the bucket to contain a minimum of
    // one elements
    sample1.rehash(1);

    // inserts key and element
    // in sample1
    sample1.insert({ 'a', 'A' });
    sample1.insert({ 'g', 'G' });

    // inserts key and element
    // in sample1

    // the sample1 size is reserved for
    // the bucket to contain a minimum of
    // three elements
    sample2.rehash(3);

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

**参考:**T2【http://www . cplusplus . com/Reference/unordered _ map/unordered _ multimap/rehash/