# 如何在 C++ 中创建元组的无序 _ 映射？

> 原文:[https://www . geeksforgeeks . org/如何创建 c 中元组的无序映射/](https://www.geeksforgeeks.org/how-to-create-an-unordered_map-of-tuples-in-c/)

[<u>元组</u>](https://www.geeksforgeeks.org/tuples-in-c/)–元组是可以容纳多个元素的对象。元素可以是不同的数据类型。元组的元素按照被访问的顺序被初始化为参数。

[<u>【无序映射】</u>](https://www.geeksforgeeks.org/unordered_map-in-cpp-stl/) 不包含元组的[散列函数](https://www.geeksforgeeks.org/hashing-data-structure/)。因此，如果我们想要散列一个元组，那么我们必须显式地为它提供一个可以散列元组的散列函数。

无序映射最多可以包含 5 个参数:

*   **键**:键值类型。
*   **值**:根据密钥存储的值的类型。
*   **散列函数**:用于散列给定密钥的函数。如果没有提供，它使用默认的散列函数。
*   **Pred** :一种函数，用于保证两个密钥不能有相同的哈希值。
*   **Alloc** :用于定义地图内存模型的对象。

hash_function 可以是任何东西，只要它可以对给定的密钥进行散列。

**语法:**

> 无序 _ 映射<tuple data_type="">，数据 _ 类型，hash _ function > map _ of _ tuple</tuple>

## C++

```cpp
// CPP program to demonstrate implementation
// of unordered_map for a tuple.

#include <bits/stdc++.h>
using namespace std;

// A hash function used to hash a tuple
struct hash_tuple {

    template <class T1, class T2, class T3>

    size_t operator()(
        const tuple<T1, T2, T3>& x)
        const
    {
        return get<0>(x)
               ^ get<1>(x)
               ^ get<2>(x);
    }
};

int main()
{

    // Sending the hash function
    // as a third argument
    unordered_map<tuple<int, int, int>,
                  bool, hash_tuple>
        mapOfTuple;

    // Creating some tuples to be used as keys
    tuple<int, int, int> t1(100, 200, 300);
    tuple<int, int, int> t2(400, 500, 600);
    tuple<int, int, int> t3(700, 800, 900);

    // Inserting values
    // in the unordered_map
    mapOfTuple[t1] = true;
    mapOfTuple[t2] = false;
    mapOfTuple[t3] = true;

    cout << "Contents of the unordered_map: \n";
    for (auto p : mapOfTuple)
        cout << "[" << get<0>(p.first) << ", "
             << get<1>(p.first) << ", "
             << get<2>(p.first)
             << "] ==> " << p.second << "\n";

    return 0;
}
```

**Output**

```cpp
Contents of the unordered_map: 
[700, 800, 900] ==> 1
[100, 200, 300] ==> 1
[400, 500, 600] ==> 0

```

> **注意:**不需要在映射中传递散列函数，它是一个自平衡 BST。按顺序的话，映射<元组<数据类型，数据类型，数据类型>，数据类型> mp 工作正常。