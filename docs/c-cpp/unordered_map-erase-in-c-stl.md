# c++ STL 中的无序 _ 贴图擦除

> 原文:[https://www.geeksforgeeks.org/unordered_map-erase-in-c-stl/](https://www.geeksforgeeks.org/unordered_map-erase-in-c-stl/)

**擦除**功能用于从无序 _ 映射中擦除元素。无序映射支持三种擦除功能:

1.  **通过迭代器擦除**:它以迭代器为参数，擦除迭代器中的键和值。
    **语法**

    ```cpp
    unordered_map.erase(const iterator);
    ```

2.  **按键擦除**:以一个按键为参数，擦除按键和值。
    **语法**

    ```cpp
    unordered_map.erase(const key);
    ```

3.  **按范围擦除**:它以两个迭代器为参数，擦除其间存在的所有键和值(包括起始迭代器，不包括结束迭代器)。
    **语法:**

    ```cpp
    unordered_map.erase(const iteratorStart, const iteratorEnd);
    ```

```cpp
// CPP program to demonstrate implementation of
// erase function in unordered_map.
#include <bits/stdc++.h>
using namespace std;

int main()
{

    unordered_map<int, bool> um;

    // Adding some elements in the map.
    um[12] = true;
    um[4189] = false;
    um[519] = true;
    um[40] = false;
    um[4991] = true;

    cout << "Contents of the unordered_map : \n";
    for (auto p : um)
        cout << p.first << "==>" << p.second << "\n";
    cout << "\n";

    // erase by iterator
    cout << "After erasing by Iterator : \n";
    um.erase(um.begin());
    for (auto p : um)
        cout << p.first << "==>" << p.second << "\n";
    cout << "\n";

    // erase by value
    cout << "After erasing by Key : \n";
    um.erase(4189);
    for (auto p : um)
        cout << p.first << "==>" << p.second << "\n";
    cout << "\n";

    // erase by range
    cout << "After erasing by Range : \n";
    auto it = um.begin();
    it++ ; // Returns iterator pointing to second element
    um.erase(it, um.end());
    for (auto p : um)
        cout << p.first << "==>" << p.second << "\n";
    cout << "\n";

    return 0;
}
```

**Output:**

```cpp
Contents of the unordered_map :
4991==>1
519==>1
40==>0
12==>1
4189==>0

After erasing by Iterator :
519==>1
40==>0
12==>1
4189==>0

After erasing by Key :
519==>1
40==>0
12==>1

After erasing by Range :
519==>1

```