# c++ STL 中的无序 _ 地图侵位 _ 提示()函数

> 原文:[https://www . geesforgeks . org/unordered _ map-侵位 _hint-function-in-c-stl/](https://www.geeksforgeeks.org/unordered_map-emplace_hint-function-in-c-stl/)

**[无序 _ 映射](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/)::侵位 _ 提示()**是 C++ STL 中的一个内置函数，它使用给定的提示在无序 _ 映射容器中插入键及其元素。它有效地将容器大小增加了一，因为无序映射是存储带有元素值的键的容器。所提供的提示并不影响要输入的位置，它只是增加了插入的速度，因为它指向开始搜索排序的位置。它以容器后面的相同顺序插入。它的工作原理类似于无序地图::定位()函数，但如果用户提供准确的位置，它有时会比它快。如果元素已经存在于地图容器中，则不会插入带有该元素的关键字，因为地图只存储唯一的关键字。

**语法:**

```cpp
unordered_map_name.emplace_hint(position, key, element)

```

**参数:**该功能接受以下参数，如下所述。

*   **位置:**指定开始排序搜索操作的位置，从而加快插入速度。
*   **键:**指定要插入无序 _ 映射容器的键。
*   **元素:**指定要插入无序映射容器的键的元素。

**返回类型:**此功能不返回任何内容。

**时间复杂度:最坏情况下** O(n)。

下面的程序说明了侵位提示()方法:

**例 1:**

```cpp
// C++ program to illustrate the
// unordered_map::emplace_hint() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    unordered_map<int, int> mp;

    // insert elements in random order
    mp.emplace_hint(mp.begin(), 2, 30);
    mp.emplace_hint(mp.begin(), 1, 40);
    mp.emplace_hint(mp.begin(), 3, 60);

    // prints the elements
    cout << "\nThe unordered_map is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.begin(); itr != mp.end(); itr++)
        cout << itr->first << "\t"
             << itr->second << endl;

    return 0;
}
```

**Output:**

```cpp
The unordered_map is : 
KEY    ELEMENT
3    60
2    30
1    40

```

**例 2**

```cpp
// C++ program to illustrate the
// unordered_map::emplace_hint() function

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    unordered_map<char, int> mp;

    // insert elements in random order
    mp.emplace_hint(mp.begin(), 'b', 30);
    mp.emplace_hint(mp.begin(), 'a', 40);
    mp.emplace_hint(mp.begin(), 'c', 60);

    // prints the elements
    cout << "\nThe unordered_map is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.begin(); itr != mp.end(); itr++)
        cout << itr->first << "\t"
             << itr->second << endl;

    return 0;
}
```

**Output:**

```cpp
The unordered_map is : 
KEY    ELEMENT
c    60
b    30
a    40

```