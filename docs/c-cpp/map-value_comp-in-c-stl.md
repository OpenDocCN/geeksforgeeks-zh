# 在 C++ STL 中映射 value _ comp()

> 原文:[https://www.geeksforgeeks.org/map-value_comp-in-c-stl/](https://www.geeksforgeeks.org/map-value_comp-in-c-stl/)

**std::map::value_comp()** 是 C++ STL 中的一个函数。它返回一个函数对象，用于比较 std::map::value 类型的对象。

**语法:**

```cpp
value_compare value_comp() const
```

**参数:**不接受任何参数。

**返回:**该方法返回一个函数对象，用于比较 std::map::value 类型的对象。

**时间复杂度:** O(1)

以下示例说明了 map::value_comp()方法:

**例 1:**

```cpp
// C++ program to illustrate
// map::value_comp() method

#include <iostream>
#include <map>
using namespace std;

int main()
{
    map<char, int> m = {
        { 'a', 1 },
        { 'b', 2 },
        { 'c', 3 },
        { 'd', 4 },
        { 'e', 5 },
    };

    auto last = *m.rbegin();
    auto i = m.begin();

    cout << "Map contains "
         << "following elements"
         << endl;

    do {

        cout << i->first
             << " = "
             << i->second
             << endl;
    } while (m.value_comp()(*i++, last));

    return 0;
}
```

**Output:**

```cpp
Map contains following elements
a = 1
b = 2
c = 3
d = 4
e = 5

```

**例 2:**

```cpp
// C++ Program to illustrate
// map::rbegin() method

#include <iostream>
#include <map>
using namespace std;

int main()
{

    map<char, char> m = {
        { 'a', 'A' },
        { 'b', 'B' },
        { 'c', 'C' },
        { 'd', 'D' },
        { 'e', 'E' },
    };

    auto last = *m.rbegin();
    auto i = m.begin();

    cout << "Map contains "
         << "following elements"
         << endl;

    do {

        cout << i->first
             << " = "
             << i->second
             << endl;
    } while (m.value_comp()(*i++, last));

    return 0;
}
```

**Output:**

```cpp
Map contains following elements
a = A
b = B
c = C
d = D
e = E

```