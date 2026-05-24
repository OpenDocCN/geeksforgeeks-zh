# c++ 中的 order_of_key()

> 原文:[https://www.geeksforgeeks.org/order_of_key-in-c/](https://www.geeksforgeeks.org/order_of_key-in-c/)

order_of_key()是[有序集](https://www.geeksforgeeks.org/ordered-set-gnu-c-pbds/)的内置函数，它是 C++ 中基于[策略的数据结构](https://www.geeksforgeeks.org/policy-based-data-structures-g/)。基于策略的数据结构不是 C++ 标准库的一部分，但是 g++ 编译器支持它们。

有序集是 g++ 中基于策略的数据结构，它将唯一的元素保持在有序的顺序中。它以 log(n)复杂度执行 STL 中集合数据结构执行的所有操作，并以 log(n)复杂度执行两个附加操作。

> 我们可以在这些数据结构中执行两个重要操作:
> 
> *   **order_of_key:** 集合中严格小于 k 的项目数
> *   **find_by_order:** 它返回第一个最大元素的迭代器

**order_of_key()** 函数接受一个键，并返回有序集中严格小于传递给它的键的元素数作为参数。

例如，

> 假设我们有一个集合 s : {1，5，6，17，88}，那么:
> s.order_of_key(6):严格小于 6 的元素个数为 2。
> s.order_of_key(25):严格小于 25 的元素个数为 4。

**与下界()和距离()的比较**

*   在 C++ 中，我们有 [std::distance](https://www.geeksforgeeks.org/stddistance-in-c/) ，它采用两个迭代器并计算它们之间的距离。即它们之间的元素数量。它可以是按顺序查找的替代方法，但是对于有序集，它的时间复杂度是 O(n)。
*   [lower_bound](https://www.geeksforgeeks.org/lower_bound-in-cpp/) is also an option and it takes log(n) amount of time. It returns an iterator to the first element which is not less than k. But since it returns an iterator we can never know the index or number of elements which are smaller than k.

    对于向量和线性数据结构，可以执行以下操作:

    > index =下界(k)–myvector . begin()；

    但是由于 set 是一个基于树的数据结构，我们不能执行这个操作。

下面的程序说明了 order_of_key()的实现:

```cpp
// CPP program to illustrate order_of_key()
// for policy based data structures

#include <iostream> 
using namespace std; 

// Important header files  
#include <ext/pb_ds/assoc_container.hpp> // Common file 
#include <ext/pb_ds/tree_policy.hpp> 
#include <functional> // for less 
#include <iostream> 
using namespace __gnu_pbds; 
using namespace std; 

// Declaring ordered_set
typedef tree<int, null_type, less<int>, rb_tree_tag, 
            tree_order_statistics_node_update> 
    ordered_set; 

// Driver code 
int main() 
{ 
    ordered_set mySet;

    // Inserting elements to ordered_set
    mySet.insert(5); 
    mySet.insert(2); 
    mySet.insert(6); 
    mySet.insert(4); 

    // count of elements less than 6 
    cout << "Count of elements less than 6::"
        << mySet.order_of_key(6) << endl; 

    // number 7 not in the set but it will show the 
    // index number if it was there in sorted array. 
    cout << "Count of elements less than 7 ::"
        << mySet.order_of_key(7) << endl; 

    return 0; 
} 
```

**Output:**

```cpp
Count of elements less than 6::3
Count of elements less than 7 ::4

```