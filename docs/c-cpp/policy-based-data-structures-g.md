# g++ 中基于策略的数据结构

> 原文:[https://www . geesforgeks . org/policy-based-data-structures-g/](https://www.geeksforgeeks.org/policy-based-data-structures-g/)

g++ 编译器还支持一些不属于 C++ 标准库的数据结构。这种结构称为基于策略的数据结构。这些数据结构是为高性能、灵活性、语义安全性和符合 std 中的相应容器而设计的。
要使用这些结构，必须在代码中添加以下几行:

## C++

```cpp
#include <ext/pb_ds/assoc_container.hpp>
using namespace __gnu_pbds;
```

例如，下面的代码显示了一个类似 set 的基于策略的数据结构，它可以添加/删除元素，可以在 O(logn)时间内找到小于 x 的元素数量、第 k 个最小元素等。它也可以像数组一样被索引。这个集合的特点是我们可以访问元素在排序数组中的索引。如果元素没有出现在集合中，我们得到元素在集合中的位置。

## C++

```cpp
// Program showing a policy-based data structure.
#include <ext/pb_ds/assoc_container.hpp> // Common file
#include <ext/pb_ds/tree_policy.hpp>
#include <functional> // for less
#include <iostream>
using namespace __gnu_pbds;
using namespace std;

// a new data structure defined. Please refer below
// GNU link : https://goo.gl/WVDL6g
typedef tree<int, null_type, less<int>, rb_tree_tag,
             tree_order_statistics_node_update>
    new_data_set;

// Driver code
int main()
{
    new_data_set p;
    p.insert(5);
    p.insert(2);
    p.insert(6);
    p.insert(4);

    // value at 3rd index in sorted array.
    cout << "The value at 3rd index ::"
         << *p.find_by_order(3) << endl;

    // index of number 6
    cout << "The index of number 6::" << p.order_of_key(6)
         << endl;

    // number 7 not in the set but it will show the
    // index number if it was there in sorted array.
    cout << "The index of number seven ::"
         << p.order_of_key(7) << endl;

    return 0;
}
```

输出:

```cpp
The value at 3rd index ::6
The index of number 6::3
The index of number seven ::4
```

**注意:【order _ of _ key 和 find_by_order 两个函数都是在对数时间内工作的。**

为了在有序集中插入同一元素的多个副本，请替换下面的行，

> typedef 树<int null_type="" equal="">，rb_tree_tag，tree _ order _ statistics _ node _ update > new _ data _ set；</int>

随着

> typedef 树<int null_type="">，rb_tree_tag，tree _ order _ statistics _ node _ update > new _ data _ set；</int>

## C++

```cpp
// Program showing a policy-based data structure.
#include <ext/pb_ds/assoc_container.hpp> // Common file
#include <ext/pb_ds/tree_policy.hpp>
#include <functional> // for less
#include <iostream>
using namespace __gnu_pbds;
using namespace std;

// a new data structure defined. Please refer below
// GNU link : https://goo.gl/WVDL6g
typedef tree<int, null_type, less_equal<int>, rb_tree_tag,
             tree_order_statistics_node_update>
    new_data_set;

// Driver code
int main()
{
    new_data_set p;
    p.insert(5);
    p.insert(5);
    p.insert(5);
    p.insert(2);
    p.insert(2);
    p.insert(6);
    p.insert(4);

    for (int i = 0; i < (int)p.size(); i++) {

        cout << "The element present at the index " << i
             << " is ";

        // Print element present at the ith index
        cout << *p.find_by_order(i) << ' ';
        cout << '\n';
    }

    return 0;
}
```

**Output**

```cpp
The element present at the index 0 is 2 
The element present at the index 1 is 2 
The element present at the index 2 is 4 
The element present at the index 3 is 5 
The element present at the index 4 is 5 
The element present at the index 5 is 5 
The element present at the index 6 is 6 
```