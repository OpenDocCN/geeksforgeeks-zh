# c++ STL 中的地图侵位 _ 提示()函数

> 原文:[https://www . geesforgeks . org/map-侵位 _ 提示-function-in-c-stl/](https://www.geeksforgeeks.org/map-emplace_hint-function-in-c-stl/)

**映射::侵位 _ 提示()**是 C++ STL 中的内置函数，它使用给定的提示将键及其元素插入到映射容器中。它有效地增加了一个容器的大小，因为 map 是存储带有元素值的键的容器。所提供的提示并不影响要输入的位置，它只是增加了插入的速度，因为它指向开始搜索排序的位置。它以容器后面的相同顺序插入。它的工作原理类似于[地图::定位()](https://www.geeksforgeeks.org/map-emplace-in-c-stl/)功能，但如果用户提供准确的位置，它有时会比它更快。如果元素已经存在于地图容器中，则不会插入带有该元素的关键字，因为地图只存储唯一的关键字。

**语法:**

```cpp
map_name.emplace_hint(position, key, element)

```

**参数:**该功能接受三个强制参数*键*，描述如下:

*   **键–**指定要插入到地图容器中的键。
*   **元素–**指定要插入到地图容器中的键的元素。
*   **位置–**指定开始排序搜索操作的位置，从而加快插入速度。

**返回值:**向新插入的元素返回一个迭代器。
如果因为元素已经存在而导致插入失败，将返回一个迭代器给已经存在的元素，并使用等价键。

```cpp
// C++ program to illustrate the
// map::emplace_hint() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    map<int, int> mp;

    // insert elements in random order
    mp.emplace_hint(mp.begin(), 2, 30); // faster
    mp.emplace_hint(mp.begin(), 1, 40); // faster
    mp.emplace_hint(mp.begin(), 3, 60); // slower

    // prints the elements
    cout << "\nThe map is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.begin(); itr != mp.end(); itr++)
        cout << itr->first << "\t" << itr->second << endl;

    return 0;
}
```

**Output:**

```cpp
The map is : 
KEY    ELEMENT
1    40
2    30
3    60

```