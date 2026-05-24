# c++ STL 中的 multimap::count()

> 原文:[https://www.geeksforgeeks.org/multimapcount-in-c-stl/](https://www.geeksforgeeks.org/multimapcount-in-c-stl/)

**multimap::count** 是 C++ STL 中的一个内置函数，它返回一个键在 multimap 容器中出现的次数。

**语法:**

```cpp
multimap_name.count(key)

```

**参数:**该函数接受一个强制参数*键*，该参数指定要返回其在多映射容器中的计数的键。

**返回值:**该函数返回一个键在多映射容器中出现的次数。

```cpp
// C++ function for illustration
// multimap::count() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize container
    multimap<int, int> mp;

    // insert elements in random order
    mp.insert({ 2, 30 });
    mp.insert({ 1, 40 });
    mp.insert({ 2, 60 });
    mp.insert({ 2, 20 });
    mp.insert({ 1, 50 });
    mp.insert({ 4, 50 });

    // count the number of times
    // 1 is there in the multimap
    cout << "1 exists " << mp.count(1) 
         << " times in the multimap\n";

    // count the number of times
    // 2 is there in the multimap
    cout << "2 exists " << mp.count(2) 
         << " times in the multimap\n";

    return 0;
}
```

**输出:**

```cpp
1 exists 2 times in the multimap
2 exists 3 times in the multimap

```