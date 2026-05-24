# c++ STL 中无序 _ 多 map find()函数

> 原文:[https://www . geesforgeks . org/unordered _ multimap-find-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-find-function-in-c-stl/)

**无序 _ 多映射::find()** 是 C++ STL 中的内置函数，它返回一个迭代器，该迭代器指向具有关键字 *k* 的元素之一。如果容器不包含任何带有关键字 k 的元素，那么它返回一个迭代器，该迭代器指向容器中最后一个元素之后的位置。

**语法:**

```cpp
unordered_multimap_name.find(k)
```

**参数:**该功能接受指定键的强制参数 *k* 。

**返回值:**它返回一个迭代器，该迭代器指向带有键 *k* 的元素所在的位置。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// unordered_multimap::find() function
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

    // find the element with key 1 and print
    auto it = sample.find(1);
    if (it != sample.end())
        cout << 1 << ":" << it->second << endl;
    else
        cout << "element with key 1 not found\n";

    // find the element with
    // key 2 and print
    it = sample.find(2);
    if (it != sample.end())
        cout << 2 << ":" << it->second << endl;
    else
        cout << "element with key 2 not found\n";

    // find the element with
    // key 100 and print
    it = sample.find(100);
    if (it != sample.end())
        cout << 100 << ":" << it->second << endl;
    else
        cout << "element with key 100 not found\n";
    return 0;
}
```

**Output:**

```cpp
1:2
2:6
element with key 100 not found

```

**程序 2:**

```cpp
// C++ program to illustrate the
// unordered_multimap::find()
#include <iostream>
#include <unordered_map>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<char, char> sample;

    // inserts element
    sample.insert({ 'a', 'b' });
    sample.insert({ 'a', 'b' });
    sample.insert({ 'a', 'd' });
    sample.insert({ 'b', 'e' });
    sample.insert({ 'b', 'd' });

    // find the element with
    // key r and print
    auto it = sample.find('r');
    if (it != sample.end())
        cout << "r"
             << ":" << it->second << endl;
    else
        cout << "element with key r not found\n";

    // find the element with
    // key a and print
    it = sample.find('a');
    if (it != sample.end())
        cout << 'a' << ":" << it->second << endl;
    else
        cout << "element with key a not found\n";

    // find the element with
    // key 'b' and print
    it = sample.find('b');
    if (it != sample.end())
        cout << "b"
             << ":" << it->second << endl;
    else
        cout << "element with key b not found\n";

    return 0;
}
```

**Output:**

```cpp
element with key r not found
a:d
b:d

```