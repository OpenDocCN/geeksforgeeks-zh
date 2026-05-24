# c++ STL 中无序 _ 多映射侵位()函数

> 原文:[https://www . geesforgeks . org/unordered _ multimap-侵位-function-in-c-stl/](https://www.geeksforgeeks.org/unordered_multimap-emplace-function-in-c-stl/)

**无序 _ 多 map::炮位()**是 C++ STL 中的内置函数，它在无序 _ 多 map 容器中插入一个新的{key，element}。插入会根据容器的标准在该位置自动完成。它将容器的尺寸增加了一个。

**语法:**

```cpp
unordered_multimap_name.emplace(key, element)
```

**参数:**该功能接受要插入容器中的单个强制参数*键*和*元素*。

**返回值:**返回一个迭代器，指向新插入的元素。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate
// unordered_multimap::emplace()
#include <iostream>
#include <string>
#include <unordered_map>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<int, int> sample;

    // inserts key and elements
    sample.emplace(1, 2);
    sample.emplace(1, 2);
    sample.emplace(1, 3);
    sample.emplace(4, 9);
    sample.emplace(60, 89);

    cout << "Key and Elements: \n";
    for (auto it = sample.begin(); it != sample.end(); it++)
        cout << "{" << it->first << ":" << it->second << "}\n ";

    return 0;
}
```

**Output:**

```cpp
Key and Elements: 
 {60:89}
 {4:9}
 {1:3}
 {1:2}
 {1:2}

```

**程序 2:**

```cpp
// unordered_multimap::emplace
#include <iostream>
#include <string>
#include <unordered_map>
using namespace std;

int main()
{

    // declaration
    unordered_multimap<string, string> sample;

    // inserts key and elements
    sample.emplace("gopal", "dave");
    sample.emplace("gopal", "dave");
    sample.emplace("Geeks", "C++");
    sample.emplace("multimap", "functions");
    sample.emplace("multimap", "functions");

    cout << "Key and Elements: \n";
    for (auto it = sample.begin(); it != sample.end(); it++)
        cout << "{" << it->first << ":" << it->second << "}\n ";

    return 0;
}
```

**Output:**

```cpp
Key and Elements: 
 {multimap:functions}
 {multimap:functions}
 {Geeks:C++}
 {gopal:dave}
 {gopal:dave}

```