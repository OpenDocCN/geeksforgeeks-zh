# 在 C++ STL 中映射插入()

> 原文:[https://www.geeksforgeeks.org/map-insert-in-c-stl/](https://www.geeksforgeeks.org/map-insert-in-c-stl/)

**映射::insert()** 是 C++ STL 中的内置函数，用于在映射容器中插入带有特定键的元素。

*   **Syntax:**

```cpp
iterator map_name.insert({key, element})

```

**参数:**该函数接受一个由要插入到地图容器中的键和元素组成的对。如果键已经存在于映射中，则函数不会在映射中插入键和元素。

**返回值:**函数返回一个迭代器，指向容器中的新元素。

以下是上述语法的图示:

## C++

```cpp
// C++ program to illustrate
// map::insert({key, element})
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

    // does not inserts key 2 with element 20
    mp.insert({ 2, 20 });
    mp.insert({ 5, 50 });

    // prints the elements
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
KEY    ELEMENT
1    40
2    30
3    60
5    50

```

*   **语法:**

```cpp
iterator map_name.insert(iterator position, {key, element})

```

**参数:**该函数接受两个参数，如下所述:

*   **{key, element}:** This specifies a pair of parameters consisting of *key* and *element* to be inserted into the map container.
*   **Location:** This does not specify the location to be inserted, but only points to the location to start the search operation to make the process faster. Insertion is done according to the order followed by the map container.

**返回值:** 函数返回一个迭代器，指向容器中的新元素。

下面是上面语法的图解:

## c++

```cpp
// C++ program to illustrate
// map::insert(iteratorposition, {key, element})
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    map<int, int> mp;

    // insert elements in random order
    mp.insert({ 2, 30 });
    mp.insert({ 1, 40 });

    auto it = mp.find(2);

    // inserts {3, 60} starting the search from
    // position where 2 is present
    mp.insert(it, { 3, 60 });

    // prints the elements
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp.begin(); itr != mp.end(); ++ itr) {
        cout << itr->first
            << '\t' << itr->second << '\n';
    }
    return 0;
}
```

**输出:**

```cpp
KEY    ELEMENT
1    40
2    30
3    60

```

*   **Syntax:**

```cpp
iterator map_name.insert(iterator position1, iterator position2)

```

**参数:**该函数接受两个参数*位置 1* 和*位置 2* ，指定元素的范围。范围**【位置 1，最后)**中的所有元素都被插入到另一个地图容器中。

**返回值:**函数返回一个迭代器，指向容器中的新元素。

下面是上面语法的图解:

T3】c++ T5

```cpp
// C++ program to illustrate
// map::insert(iteratorposition1, iteratorposition2)
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    map<int, int> mp, mp1;

    // insert elements in random order
    mp.insert({ 2, 30 });
    mp.insert({ 1, 40 });

    // inserts all elements in range
    // [begin, end) in mp1
    mp1.insert(mp.begin(), mp.end());

    // prints the elements
    cout << "Elements in mp1 are\n";
    cout << "KEY\tELEMENT\n";
    for (auto itr = mp1.begin(); itr != mp1.end(); ++ itr) {
        cout << itr->first
             << '\t' << itr->second << '\n';
    }
    return 0;
}
```

T6T8**输出:**T1

T12