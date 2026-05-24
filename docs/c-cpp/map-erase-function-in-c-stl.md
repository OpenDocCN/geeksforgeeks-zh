# c++ STL 中的贴图擦除()功能

> 原文:[https://www.geeksforgeeks.org/map-erase-function-in-c-stl/](https://www.geeksforgeeks.org/map-erase-function-in-c-stl/)

**map::erase()** 是 C++ STL 中的内置函数，用于从容器中擦除元素。它可以用来擦除任何指定位置或给定范围的键和元素。

*   **擦除键的语法:**

```cpp
map_name.erase(key)

```

**参数:**该功能接受一个强制参数*键*，指定要在地图容器中擦除的键。

**返回值:**如果在地图中找到关键元素，函数返回 1，否则返回 0。

下面的程序说明了上面的语法:

## C++

```cpp
// C++ program to illustrate
// map::erase(key)
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    map<int, int> mp;

    // insert elements in random order
    mp.insert({ 2, 30 });
    mp.insert({ 1, 40 });
    mp.insert({ 3, 60 });
    mp.insert({ 5, 50 });

    // prints the elements
    cout << "The map before using erase() is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.begin(); itr != mp.end(); ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }

    // function to erase given keys
    mp.erase(1);
    mp.erase(2);

    // prints the elements
    cout << "\nThe map after applying erase() is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.begin(); itr != mp.end(); ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }
    return 0;
}
```

**Output:** 

```cpp
The map before using erase() is : 
KEY    ELEMENT
1    40
2    30
3    60
5    50

The map after applying erase() is : 
KEY    ELEMENT
3    60
5    50

```

*   **移除位置的语法:**

```cpp
map_name.erase(iterator position)

```

**参数:**函数接受一个强制参数*位置*，该位置指定了迭代器，该迭代器是对要擦除的元素位置的引用。

**返回值:**函数不返回任何内容。

下面的程序说明了上面的语法:

## C++

```cpp
// C++ program to illustrate
// map::erase(iteratorposition)
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    map<int, int> mp;
    // insert elements in random order
    mp.insert({ 2, 30 });
    mp.insert({ 1, 40 });
    mp.insert({ 3, 60 });
    mp.insert({ 5, 50 });

    // prints the elements
    cout << "The map before using erase() is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.begin(); itr != mp.end(); ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }

    // function to erase given position
    auto it = mp.find(2);
    mp.erase(it);

    auto it1 = mp.find(5);
    mp.erase(it1);

    // prints the elements
    cout << "\nThe map after applying erase() is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.begin(); itr != mp.end(); ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }
    return 0;
}
```

**Output:** 

```cpp
The map before using erase() is : 
KEY    ELEMENT
1    40
2    30
3    60
5    50

The map after applying erase() is : 
KEY    ELEMENT
1    40
3    60

```

*   **擦除给定范围的语法:**

```cpp
map_name.erase(iterator position1, iterator position2)

```

**参数:**该功能接受两个强制参数，如下所述:

*   **位置 1**–指定迭代器，该迭代器是要移除的元素的引用。
*   **位置 2**–指定迭代器，该迭代器是要移除的元素的引用。

**返回值:**函数不返回任何内容。它移除给定迭代器范围内的所有元素。

下面的程序说明了上面的语法:

## C++

```cpp
// C++ program to illustrate
// map::erase(iteratorposition1, iteratorposition2)
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    map<int, int> mp;
    // insert elements in random order
    mp.insert({ 2, 30 });
    mp.insert({ 1, 40 });
    mp.insert({ 3, 60 });
    mp.insert({ 2, 20 });
    mp.insert({ 5, 50 });

    // prints the elements
    cout << "The map before using erase() is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.begin(); itr != mp.end(); ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }

    // function to erase in a given range
    // find() returns the iterator reference to
    // the position where the element is
    auto it1 = mp.find(2);
    auto it2 = mp.find(5);
    mp.erase(it1, it2);

    // prints the elements
    cout << "\nThe map after applying erase() is : \n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.begin(); itr != mp.end(); ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }
    return 0;
}
```

**Output:** 

```cpp
The map before using erase() is : 
KEY    ELEMENT
1    40
2    30
3    60
5    50

The map after applying erase() is : 
KEY    ELEMENT
1    40
5    50

```