# 如何在 C++ 中创建成对的无序 _ 映射？

> 原文:[https://www . geeksforgeeks . org/如何创建无序的 c 对地图/](https://www.geeksforgeeks.org/how-to-create-an-unordered_map-of-pairs-in-c/)

[无序映射](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/)不像对 int、string 等那样包含对一对的散列函数，所以如果我们想要散列一对，那么我们必须显式地为它提供一个可以散列一对的散列函数。无序映射最多可包含 5 个参数:

*   Key: key value type
*   Value: the value type stored according to the key.
*   Hash function: The function used to hash the given key. If not provided, it uses the default hash function.
*   Pred: a function that is used so that no two keys can have the same hash value.
*   Alloc: an object that defines the mapped memory model.

hash_function 可以是任何东西，只要它可以对给定的密钥进行散列。

先决条件:[如何创建自定义类的无序 _ 映射？](https://www.geeksforgeeks.org/how-to-create-an-unordered_map-of-user-defined-class-in-cpp/)

```cpp
// CPP program to demonstrate implementation of
// unordered_map for a pair.
#include <bits/stdc++.h>
using namespace std;

// A hash function used to hash a pair of any kind
struct hash_pair {
    template <class T1, class T2>
    size_t operator()(const pair<T1, T2>& p) const
    {
        auto hash1 = hash<T1>{}(p.first);
        auto hash2 = hash<T2>{}(p.second);
        return hash1 ^ hash2;
    }
};

int main()
{
    // Sending the hash function as a third argument
    unordered_map<pair<int, int>, bool, hash_pair> um;

    // Creating some pairs to be used as keys
    pair<int, int> p1(1000, 2000);
    pair<int, int> p2(2000, 3000); 
    pair<int, int> p3(2005, 3005); 

    // Inserting values in the unordered_map.
    um[p1] = true;
    um[p2] = false;
    um[p3] = true;

    cout << "Contents of the unordered_map : \n";
    for (auto p : um)
        cout << "[" << (p.first).first << ", " 
             << (p.first).second << "] ==> "
             << p.second << "\n";

    return 0;
}
```

**输出:**

```cpp
Contents of the unordered_map : 
[1000, 2000] ==> 1
[2005, 3005] ==> 1
[2000, 3000] ==> 0

```