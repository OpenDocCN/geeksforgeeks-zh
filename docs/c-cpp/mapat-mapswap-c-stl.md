# c++ STL 中的 map::at()和 map::swap()

> 哎哎哎::1230【https://www . geeksforgeeks . org/mapat-map WAP-c-STL/

地图是 STL 中的容器，用于以**键值**对的形式存储元素。在内部，地图中的元素总是按其键*排序*。地图主要实现为*二分搜索法树*。

**map::at()**
at()函数用于返回对与键 **k** 关联的元素的引用。

**语法:**

```cpp
map1.at(k)

Parameters:
k is the Key value of the 
element whose associated value is accessed.

```

**Return:** 返回一个对元素关联值的引用，该元素的键值相当于 **k** 。

**示例:**

```cpp
Input:  map1 = {
                 {1, 'a'},
                 {2, 'b'},
                 {3, 'c'},
                 {4, 'd'}
               }
        map1.at(2);
Output: b

Input:  map2 = {
                 {'w', 1},
                 {'x', 2},
                 {'y', 3}
               }
        map2.at('w');
Output: 1

```

```cpp
// CPP program to illustrate
// Implementation of swap() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Take any two maps
    map<int, char> map1;
    map<char, int> map2;

    map1[1] = 'a';
    map1[2] = 'b';
    map1[3] = 'c';
    map1[4] = 'd';

    map2['w'] = 1;
    map2['y'] = 2;
    map2['z'] = 3;

    // Print the associated element
    cout << "Element at map1[2] = "
         << map1.at(2) << endl;

    cout << "Element at map2['w'] = "
         << map2.at('w') << endl;

    return 0;
}
```

**输出:**

```cpp
Element at map1[2] = b
Element at map2['w'] = 1

```

**地图::swap()**
swap()函数用于交换两张地图的内容，但地图必须是**相同类型的**，尽管大小可能不同。
**语法:**

```cpp
map1.swap(map2)
       OR
swap(map1, map2)

Parameters:
map1 is the first map object.
map2 is the second map object.

```

**返回值:**无

**示例:**

```cpp
Input : map1 = {
                 {1, 'a'},
                 {2, 'b'},
                 {3, 'c'},
                 {4, 'd'}
               }
        map2 = {
                 {5, 'w'},
                 {6, 'x'},
                 {7, 'y'}
               }
 swap(map1, map2)

Output : map1 = {
                 {5, 'w'},
                 {6, 'x'},
                 {7, 'y'}
                }
         map2 = {
                 {1, 'a'},
                 {2, 'b'},
                 {3, 'c'},
                 {4, 'd'}
                }

```

```cpp
// CPP program to illustrate
// Implementation of swap() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Take any two maps
    map<int, char> map1, map2;

    map1[1] = 'a';
    map1[2] = 'b';
    map1[3] = 'c';
    map1[4] = 'd';

    map2[5] = 'w';
    map2[6] = 'x';
    map2[7] = 'y';

    // Swap elements of queues
    swap(map1, map2);

    // Print the elements of maps
    cout << "map1:\n"
         << "\tKEY\tELEMENT\n";
    for (auto it = map1.begin();
         it != map1.end(); it++)

        cout << "\t" << it->first << "\t" << it->second << '\n';

    cout << "map2:\n"
         << "\tKEY\tELEMENT\n";
    for (auto it = map2.begin();
         it != map2.end(); it++)

        cout << "\t" << it->first << "\t" << it->second << '\n';

    return 0;
}
```

**输出:**

```cpp
map1:
    KEY    ELEMENT
    5    w
    6    x
    7    y
map2:
    KEY    ELEMENT
    1    a
    2    b
    3    c
    4    d

```