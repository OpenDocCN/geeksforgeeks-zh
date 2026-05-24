# c++ STL 中无序 _ 多地图侵位 _ 提示()函数

> 原文:[https://www . geesforgeks . org/unordered _ multimap-侵位 _hint-function-in-c-stl/](https://www.geeksforgeeks.org/unordered_multimap-emplace_hint-function-in-c-stl/)

**无序 _ 多 map::侵位 _ 提示()**是 C++ STL 中的内置函数，它在无序 _ 多 map 容器中插入一个新的{key:element}。它从参数中提供的位置开始搜索元素的插入点。位置只是一个提示，它并不决定插入的位置。插入会根据容器的标准在该位置自动完成。它将容器的尺寸增加了一个。

**语法:**

```cpp
*unordered_multimap_name.emplace_hint*(iterator position, key, element)
```

**参数:**该功能接受三个强制参数，描述如下:

*   **位置:**指定迭代器指向插入搜索操作开始的位置。
*   **键:**指定要插入容器的键。
*   **元素:**指定要插入容器的元素

**返回值:**返回一个迭代器，指向新插入的元素。

以下程序说明了上述功能:

**程序 1:**

## C++

```cpp
// C++ program to illustrate
// unordered_multimap::emplace_hint()
#include <iostream>
#include <string>
#include <unordered_map>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<int, int> sample;

    // inserts key and element in a faster
    // way as hint given is correct
    auto it = sample.emplace_hint(sample.begin(), 1, 2);
    it = sample.emplace_hint(it, 1, 2);
    it = sample.emplace_hint(it, 1, 3);

    // slower methods as wrong position
    // has been given to start
    sample.emplace_hint(sample.begin(), 4, 9);
    sample.emplace_hint(sample.begin(), 60, 89);

    std::cout << "Key and elements:\n";
    for (auto it = sample.begin(); it != sample.end(); it++)
        cout << "{" << it->first << ":" << it->second << "}\n ";

    std::cout << std::endl;
    return 0;
}
```

**Output:** 

```cpp
Key and elements:
{60:89}
 {4:9}
 {1:2}
 {1:2}
 {1:3}
```

**程序 2:**

## C++

```cpp
// C++ program to illustrate
// unordered_multimap::emplace_hint()
#include <iostream>
#include <string>
#include <unordered_map>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<string, string> sample;

    // inserts elements in a faster way as
    // hint given is correct
    auto it = sample.emplace_hint(sample.begin(), "gopal", "dave");
    it = sample.emplace_hint(it, "gopal", "dave");
    it = sample.emplace_hint(it, "Geeks", "Website");

    // slower methods as wrong position
    // has been given to start
    sample.emplace_hint(sample.begin(), "Geeks", "STL");
    sample.emplace_hint(sample.begin(), "Multimap", "functions");

    std::cout << "Key and elements:\n";
    for (auto it = sample.begin(); it != sample.end(); it++)
        cout << "{" << it->first << ":" << it->second << "}\n ";

    std::cout << std::endl;
    return 0;
}
```

**Output:** 

```cpp
Key and elements:
{Multimap:functions}
 {Geeks:Website}
 {Geeks:STL}
 {gopal:dave}
 {gopal:dave}
```