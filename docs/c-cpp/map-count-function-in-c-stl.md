# c++ STL 中的 map count()函数

> 原文:[https://www.geeksforgeeks.org/map-count-function-in-c-stl/](https://www.geeksforgeeks.org/map-count-function-in-c-stl/)

**map::count()** 是 C++ STL 中的一个内置函数，如果在 map 容器中存在带有 key K 的元素，则返回 1。如果容器中不存在关键字为 K 的元素，则返回 0。

**语法:**

```cpp
map_name.count(key k)
```

**参数:**该函数接受一个强制参数 *k* ，该参数指定了要在地图容器中搜索的关键字。

**返回值:**该函数返回按键 K 在地图容器中出现的次数。如果密钥存在于容器中，则返回 1，因为映射只包含唯一的密钥。如果密钥不在地图容器中，则返回 0。

下面的程序说明了上面的功能:

```cpp
// C++ program to illustrate
// the map::count() function
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
    mp.insert({ 4, 20 });
    mp.insert({ 5, 50 });

    // checks if key 1 is present or not
    if (mp.count(1))
        cout << "The key 1 is present\n";
    else
        cout << "The key 1 is not present\n";

    // checks if key 100 is present or not
    if (mp.count(100))
        cout << "The key 100 is present\n";
    else
        cout << "The key 100 is not present\n";

    return 0;
}
```

**输出:**

```cpp
The key 1 is present
The key 100 is not present

```