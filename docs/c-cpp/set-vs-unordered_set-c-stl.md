# 集合 vs c++ STL 中的无序 _ 集合

> 原文:[https://www.geeksforgeeks.org/set-vs-unordered_set-c-stl/](https://www.geeksforgeeks.org/set-vs-unordered_set-c-stl/)

先决条件:[设置在 C++ ](https://www.geeksforgeeks.org/set-in-cpp-stl/) ，[无序 _ 设置在 C++ ](https://www.geeksforgeeks.org/unorderd_set-stl-uses/)

**差异:**

```cpp
                |     set             | unordered_set
---------------------------------------------------------
Ordering        | increasing  order   | no ordering
                | (by default)        |

Implementation  | Self balancing BST  | Hash Table
                | like Red-Black Tree |  

search time     | log(n)              | O(1) -> Average 
                |                     | O(n) -> Worst Case

Insertion time  | log(n) + Rebalance  | Same as search

Deletion time   | log(n) + Rebalance  | Same as search

```

**使用设定时**

*   我们需要有序的数据。
*   我们必须打印/访问数据(按排序顺序)。
*   我们需要元素的前身/继承者。
*   由于集合是有序的，我们可以在集合元素上使用类似 [binary_search()，下界()和上界()](https://www.geeksforgeeks.org/binary-search-functions-in-c-stl-binary_search-lower_bound-and-upper_bound/)这样的函数。这些函数不能用于无序集()。
*   更多情况参见[BST 相对 Hash tab](https://www.geeksforgeeks.org/advantages-of-bst-over-hash-table/)e 的优势。

**使用无序 _ 设置当**

*   我们需要保留一组不同的元素，不需要排序。
*   我们需要单元素访问，即不遍历。

示例:

```cpp
set:
Input  :  1, 8, 2, 5, 3, 9
Output :  1, 2, 3, 5, 8, 9

Unordered_set:
Input  : 1, 8, 2, 5, 3, 9
Output : 9 3 1 8 2 5 

```

如果要看 c++ STL 中 set 和无序 _set 的实现细节，参见 [Set Vs Map](https://www.geeksforgeeks.org/set-vs-map-c-stl/) 。Set 允许按排序顺序遍历元素，而 Unordered_set 不允许按排序顺序遍历元素。

```cpp
// Program to print elements of set
#include <bits/stdc++.h>
using namespace std;

int main()
{
    set<int> s;
    s.insert(5);
    s.insert(1);
    s.insert(6);
    s.insert(3);
    s.insert(7);
    s.insert(2);

    cout << "Elements of set in sorted order: \n";
    for (auto it : s)
        cout << it << " ";

    return 0;
}
```

**Output:**

```cpp
Elements of set in sorted order: 
1 2 3 5 6 7

```

```cpp
// Program to print elements of set
#include <bits/stdc++.h>
using namespace std;

int main()
{
    unordered_set<int> s;
    s.insert(5);
    s.insert(1);
    s.insert(6);
    s.insert(3);
    s.insert(7);
    s.insert(2);

    cout << "Elements of unordered_set: \n";
    for (auto it : s)
        cout << it << " ";

    return 0;
}
```

**Output:**

```cpp
Elements of unordered_set: 
2 7 5 1 6 3

```

*中的【前任/继任者】 :可以修改
集合来查找前任或继任者，而无序 _ 集合不允许查找前任/继任者。*

```cpp
*// Program to print inorder predecessor and inorder successor
#include <bits/stdc++.h>
using namespace std;

set<int> s;

void inorderPredecessor(int key)
{
    if (s.find(key) == s.end()) {
        cout << "Key doesn't exist\n";
        return;
    }

    set<int>::iterator it;
    it = s.find(key); // get iterator of key

    // If iterator is at first position
    // Then, it doesn't have predecessor
    if (it == s.begin()) {
        cout << "No predecessor\n";
        return;
    }

    --it; // get previous element
    cout << "predecessor of " << key << " is=";
    cout << *(it) << "\n";
}

void inorderSuccessor(int key)
{
    if (s.find(key) == s.end()) {
        cout << "Key doesn't exist\n";
        return;
    }

    set<int>::iterator it;
    it = s.find(key); // get iterator of key
    ++ it; // get next element

    // Iterator points to NULL (Element does
    // not exist)
    if (it == s.end())
    {
        cout << "No successor\n";
        return;
    }
    cout << "successor of " << key << " is=";
    cout << *(it) << "\n";
}

int main()
{
    s.insert(1);
    s.insert(5);
    s.insert(2);
    s.insert(9);
    s.insert(8);

    inorderPredecessor(5);
    inorderPredecessor(1);
    inorderPredecessor(8);
    inorderSuccessor(5);
    inorderSuccessor(2);
    inorderSuccessor(9);

    return 0;
}*
```

***Output:**

```cpp
predecessor of 5 is=2
No predecessor
predecessor of 8 is=5
successor of 5 is=8
successor of 2 is=5
No successor

```*