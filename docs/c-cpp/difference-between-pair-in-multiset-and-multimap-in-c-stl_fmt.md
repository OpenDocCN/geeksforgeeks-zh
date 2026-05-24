# C++ STL 中 multiset 和 multimap 对 pair 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-pair-in-multiset-and-multimap-in-c-stl/](https://www.geeksforgeeks.org/difference-between-pair-in-multiset-and-multimap-in-c-stl/)

## Pairs in C++

[`pair`](https://www.geeksforgeeks.org/pair-in-cpp-stl/) 容器是在 `<utility>` 头中定义的简单容器，由两个数据元素或对象组成。第一个元素被称为 `first`，第二个元素被称为 `second`，顺序是固定的 (`first`, `second`)。`pair` 用于将两个类型可能不同的值组合在一起。`pair` 提供了一种将两个异构对象存储为一个单元的方法。

**语法:**

> `pair<data_type1, data_type2> pair_name;`

## Multiset in C++

[`multiset`](https://www.geeksforgeeks.org/multiset-in-cpp-stl/) 是一种关联容器，按照特定的顺序存储元素，多个元素可以具有相同的值。

**语法:**

> `multiset<data_type> multiset_name;`

## Multimap in C++

[`multimap`](https://www.geeksforgeeks.org/multimap-associative-containers-the-c-standard-template-library-stl/) 是一种关联容器，类似于 [`map`](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)，不同的是多个元素可以有相同的键。

**语法:**

> `multimap<data_type1, data_type2> multimap_name;`

## multiset 的 pair 和 [C++ STL](https://www.geeksforgeeks.org/the-c-standard-template-library-stl/) multimap 有什么区别？

这两种数据结构 `multiset` 和 `multimap` 的默认行为是以升序存储元素。当创建一个 `pair` 的 `multiset` 时，默认情况下，它将根据所有 `pair` 的 `first` 元素按照递增顺序对所有的 `pair` 进行排序，如果任意两对或两对以上 `pair` 的 `first` 元素相等，则它将根据 `pair` 的 `second` 元素对该 `pair` 进行排序。

默认情况下，当创建一个 `pair` 的 `multimap` 时，它将根据所有 `pair` 的 `first` 元素对所有 `pair` 进行排序，如果任意两个或两个以上 `pair` 的 `first` 元素相等，则它将根据插入到 `multimap` 的顺序打印该 `pair`。

以下是说明差异的程序:

### 程序 1: multiset 的 pair

```cpp
// C++ program print the data of
// multiset by inserting using pair
#include <bits/stdc++.h>
using namespace std;

// Function to print the data stored
// in pair of multiset
void printData(multiset<pair<int, string> > gfg)
{
    // Declare iterator
    multiset<pair<int, string> >::iterator i;

    // Iterate through pair of multiset
    for (i = gfg.begin(); i != gfg.end(); ++i) {
        // Print the pairs
        cout << i->first << " "
             << i->second << endl;
    }
}

// Driver Code
int main()
{
    // Declare pair of multiset
    multiset<pair<int, string> > gfg;

    // Insert Data
    gfg.insert(make_pair(1, "yukti"));
    gfg.insert(make_pair(2, "umang"));
    gfg.insert(make_pair(3, "vinay"));
    gfg.insert(make_pair(3, "vijay"));
    gfg.insert(make_pair(4, "kanak"));

    // Function call to print the data
    printData(gfg);
    return 0;
}
```

**说明:**
在上面的程序中我们创建了 `pair` 的整数和字符串，其中名称与每个整数配对，并插入到 `multiset` 中。根据 `multiset` 默认行为，数据按照 `first` 元素按照升序的顺序排列，但是当 `first` 元素相同时会按照 `second` 值排列这些元素。对于 `pair(3, "vijay")` 和 `pair(3, "vinay")` 而言，`pair` 中的第一个元素，即 `3` 对于 `"vijay"` 和 `"vinay"` 都是相同的，因此它将根据第二个元素 `"vijay"` 然后 `"vinay"` 来排列 `pair` (按字母顺序)。

### 程序 2: multimap 的 pair

```cpp
// C++ program print the data of
// multimap by inserting using pair
#include <bits/stdc++.h>
using namespace std;

// Function to print the data stored
// in pair of multimap
void printData(multimap<int, string> gfg)
{
    // Declare iterator
    multimap<int, string>::iterator i;

    // Iterate through pair of multiset
    for (i = gfg.begin(); i != gfg.end(); ++i) {
        // Print the pairs
        cout << i->first << " "
             << i->second << endl;
    }
}

// Driver Code
int main()
{
    // Declare pair of multimap
    multimap<int, string> gfg;

    // Insert data
    gfg.insert(make_pair(1, "yukti"));
    gfg.insert(make_pair(2, "umang"));
    gfg.insert(make_pair(3, "vinay"));
    gfg.insert(make_pair(3, "vijay"));
    gfg.insert(make_pair(4, "kanak"));

    // Function call to print the data
    printData(gfg);

    return 0;
}
```

**Output**

```cpp
1 yukti
2 umang
3 vinay
3 vijay
4 kanak
```

**以上代码解释:**
在上面的程序中，我们再次插入了相同的 `pair` 但是这次是在 `multimap` 中。根据 `multimap` 的默认行为，数据按照键按照升序排列，但是当键相同时，与 `multiset` 不同，它会优先考虑哪个元素先插入，然后按照这个顺序排列。因此，如所示的输出中，我们可以看到，由于键 `3` 对于 `"vinay"` 和 `"vijay"` 是相同的，因此它将遵循 `pair` 插入到 `multimap` 中的顺序，这就是为什么在输出中，`"vinay"` 排在 `"vijay"` 之前。

### 表格区分

| Multiset 的 Pair | Multimap |
| --- | --- |
| `multiset` 的 `pair` 用于将键映射到特定的值。 | 默认行为是插入键值对元素。 |
| 当创建一个 `multiset` 时，默认情况下，它将根据所有 `pair` 的 `first` 元素按照升序对所有的 `pair` 进行排序，如果任意两对或两对以上 `pair` 的 `first` 元素相等，则它将根据 `pair` 的 `second` 元素对该 `pair` 进行排序。 | 当创建一个 `multimap` 时，默认情况下，它将根据所有 `pair` 的 `first` 元素对所有 `pair` 进行排序。如果任意两个或两个以上 `pair` 的 `first` 元素相等，则它将根据插入到 `multimap` 的顺序打印该 `pair`。 |
| 语法:<br>> `multiset<pair<int, string>> M;` | 语法:<br>> `multimap<int, string> M;` |