# 在 C++ STL 中映射 key_comp()函数

> 原文:[https://www . geesforgeks . org/map-key _ comp-function-in-c-STL/](https://www.geeksforgeeks.org/map-key_comp-function-in-c-stl/)

**映射::key_comp()** 是 C++ 中 STL 中的一个函数，它返回比较键的容器所使用的比较对象的副本。

**语法:**

```cpp
map.key_comp()
```

**返回值:**该方法返回比较关键字的容器使用的比较对象。

以下示例说明了 key_comp()方法的工作原理:

**示例:**

```cpp
// C++ program to demonstrate map::key_comp().

#include <iostream>
#include <map>
using namespace std;

int main()
{
    // Declare the map
    map<char, int> mymap;

    // Compare the key.
    map<char, int>::key_compare
        mycomp
        = mymap.key_comp();

    // Populate the map
    mymap['x'] = 50;
    mymap['y'] = 100;
    mymap['z'] = 150;

    // Print the map
    cout << "mymap contain:\n";

    char highest = mymap.rbegin()->first;

    // key value of last element
    map<char, int>::iterator
        it
        = mymap.begin();

    do {
        cout << it->first
             << " => " << it->second
             << "\n";
    } while (mycomp((*it++).first, highest));

    cout << "\n";

    return 0;
}
```

**Output:**

```cpp
mymap contain:
x => 50
y => 100
z => 150

```

**例 2:**

```cpp
// C++ program to demonstrate map::key_comp().

#include <iostream>
#include <map>
using namespace std;

int main()
{
    // Declare the map
    map<char, int> mymap;

    // Compare the key.
    map<char, int>::key_compare
        mycomp
        = mymap.key_comp();

    mymap['a'] = 100;
    mymap['b'] = 200;
    mymap['c'] = 300;

    cout << "mymap contain:\n";

    char highest = mymap.rbegin()->first;

    // key value of last element

    map<char, int>::iterator
        it
        = mymap.begin();

    do {
        cout << it->first
             << " => "
             << it->second
             << '\n';
    } while (mycomp((*it++).first, highest));

    cout << '\n';

    return 0;
}
```

**Output:**

```cpp
mymap contain:
a => 100
b => 200
c => 300

```