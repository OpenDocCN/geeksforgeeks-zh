# c++ STL 中的无序 _ 多映射相等 _ 范围()函数

> 原文:[https://www . geesforgeks . org/unordered _ multimap-equal _ range-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-equal_range-function-in-c-stl/)

**unordered _ multimap::equal _ range()**是 C++ STL 中的内置函数，返回所有元素的键等于一个*键*的范围。它返回一对迭代器，其中第一个迭代器指向范围的下限，第二个迭代器指向范围的上限。如果容器中没有等于给定*值*的元素，则它返回一对，其中下限和上限都指向容器结束后的位置或*无序 _ 多重映射结束()。*

**语法:**

```cpp
unordered_multimap_name.equal_range(k)
```

**参数:**该功能接受强制参数 *k* 。返回的范围将包含带有关键字 k 的元素。

**返回值:**返回一对迭代器。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multimap::equal_range()
#include <iostream>
#include <unordered_map>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<int, int> sample;

    // inserts key and element
    sample.insert({ 1, 2 });
    sample.insert({ 1, 2 });
    sample.insert({ 2, 3 });
    sample.insert({ 3, 4 });
    sample.insert({ 2, 6 });

    // iterator of pairs pointing to range
    // which includes 1 and print by iterating in range
    auto itr = sample.equal_range(1);
    cout << "Elements with Key 1: ";
    for (auto it = itr.first; it != itr.second; it++) {
        cout << it->second << " ";
    }

    cout << endl;

    // iterator of pairs pointing to range
    // which includes 2 and print by iterating in range
    itr = sample.equal_range(2);
    cout << "Elements with Key 2: ";
    for (auto it = itr.first; it != itr.second; it++) {
        cout << it->second << " ";
    }

    return 0;
}
```

**Output:**

```cpp
Elements with Key 1: 2 2 
Elements with Key 2: 6 3

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multimap::equal_range()
#include <iostream>
#include <unordered_map>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<char, char> sample;

    // inserts key and element
    sample.insert({ 'a', 'b' });
    sample.insert({ 'a', 'b' });
    sample.insert({ 'a', 'd' });
    sample.insert({ 'b', 'e' });
    sample.insert({ 'b', 'd' });

    // iterator of pairs pointing to range
    // which includes b and print by iterating in range
    auto itr = sample.equal_range('b');
    cout << "Elements with Key b: ";
    for (auto it = itr.first; it != itr.second; it++) {
        cout << it->second << " ";
    }

    cout << endl;

    // iterator of pairs pointing to range
    // which includes a and print by iterating in range
    itr = sample.equal_range('a');
    cout << "Elements with Key a: ";
    for (auto it = itr.first; it != itr.second; it++) {
        cout << it->second << " ";
    }

    return 0;
}
```

**Output:**

```cpp
Elements with Key b: d e 
Elements with Key a: d b b

```