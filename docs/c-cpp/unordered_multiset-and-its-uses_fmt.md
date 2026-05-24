# 无序多集及其用途

> 原文：[https://www.geeksforgeeks.org/unordered_multiset-and-its-uses/](https://www.geeksforgeeks.org/unordered_multiset-and-its-uses/)

我们在之前的文章中已经讨论过[无序集合](https://www.geeksforgeeks.org/unorderd_set-stl-uses/)。无序集合的问题是，在该数据结构中不可能存储重复的条目。例如，如果我们有一些值 `v` 已经在无序集中，再次插入 `v` 将没有效果。

为了处理这种复制，应该使用无序多集，它也可以存储重复的元素。在内部，当插入现有值时，数据结构会增加与每个值相关联的计数。由于每个值的计数都存储在无序多集合中，因此它比无序集合占用更多的空间（如果所有值都不同）。

无序多集的内部实现与无序集相同，也使用哈希表进行搜索，只是计数值与前一个中的每个值相关联。由于元素的散列，它没有存储元素的特定顺序，所以所有元素可以以任何顺序出现，但是重复的元素会出现在一起。无序多集上的所有操作平均需要恒定的时间，但在最坏的情况下可以达到线性。

无序多集支持许多功能，如下代码所示：

## C++示例

```cpp
// C++ program to demonstrate various function
// of unordered_multiset
#include <bits/stdc++.h>
using namespace std;

// making typedef for short declaration
typedef unordered_multiset<int>::iterator umit;

// Utility function to print unordered_multiset
void printUset(unordered_multiset<int> ums)
{
    //  begin() returns iterator to first element of set
    umit it = ums.begin();
    for (; it != ums.end(); it++)
        cout << *it << " ";
    cout << endl;
}

//  Driver program to check all function
int main()
{
    //  empty initialization
    unordered_multiset<int> ums1;

    //  Initialization by intializer list
    unordered_multiset<int> ums2 ({1, 3, 1, 7, 2, 3,
                                   4, 1, 6});

    //  Initialization by assignment
    ums1 = {2, 7, 2, 5, 0, 3, 7, 5};

    //  empty() function return true if set is empty
    // otherwise false
    if (ums1.empty())
        cout << "unordered multiset 1 is empty\n";
    else
        cout << "unordered multiset 1 is not empty\n";

    //  size() function returns total number of elements
    // in data structure
    cout << "The size of unordered multiset 2 is : "
         << ums2.size() << endl;

    printUset(ums1);

    ums1.insert(7);

    printUset(ums1);

    int val = 3;

    // find function returns iterator to first position
    // of  val, if exist otherwise it returns iterator
    // to end
    if (ums1.find(val) != ums1.end())
        cout << "unordered multiset 1 contains "
             << val << endl;
    else
        cout << "unordered multiset 1 does not contains "
             << val << endl;

    //  count function returns total number of occurrence in set
    val = 5;
    int cnt = ums1.count(val);
    cout << val << " appears " << cnt
         << " times in unordered multiset 1 \n";

    val = 9;

    //  if count return >0 value then element exist otherwise not
    if (ums1.count(val))
        cout << "unordered multiset 1 contains "
             << val << endl;
    else
        cout << "unordered multiset 1 does not contains "
             << val << endl;

    val = 1;

    // equal_range returns a pair, where first is iterator
    // to first position of val and second it iterator to
    // last position to val
    pair<umit, umit> erange_it = ums2.equal_range(val);
    if (erange_it.first != erange_it.second)
        cout << val << " appeared atleast once in "
                        "unoredered_multiset \n";

    printUset(ums2);

    // erase function deletes all instances of val
    ums2.erase(val);

    printUset(ums2);

    // clear function deletes all entries from set
    ums1.clear();
    ums2.clear();

    if (ums1.empty())
        cout << "unordered multiset 1 is empty\n";
    else
        cout << "unordered multiset 1 is not empty\n";
}
```

输出：

```cpp
unordered multiset 1 is not empty
The size of unordered multiset 2 is : 9
3 0 5 5 7 7 2 2 
3 0 5 5 7 7 7 2 2 
unordered multiset 1 contains 3
5 appears 2 times in unordered multiset 1 
unordered multiset 1 does not contains 9
1 appeared atleast once in unoredered_multiset 
6 4 2 7 3 3 1 1 1 
6 4 2 7 3 3 
unordered multiset 1 is empty
```

正如我们所看到的，大多数操作工作类似于无序集合的工作，但是需要注意的是：
`equal_range(val)` 函数返回一对类型，其中第一个迭代器指向 `val` 的第一个位置，第二个迭代器指向数据结构中 `val` 的最后一个位置。
`erase(val)` 函数从数据结构中删除其所有实例，例如，如果某个值 `v` 在 `unordered_multiset` 中出现了 `t` 次，并且在调用 `erase` 时，`v` 被完全删除，这不是多次预期的行为。

我们可以使用 `find` 函数和迭代器版本的 `erase` 只删除某个值的一个副本，由于 `find` 函数将迭代器返回到找到的值的第一个位置，我们可以将这个迭代器传递给 `erase` 而不是实际值来只删除一个副本，这样做的代码如下所示：

## 删除单个副本的示例

```cpp
//  C++ program to delete one copy from unordered set
#include <bits/stdc++.h>
using namespace std;

//  making typedef for short declaration
typedef unordered_multiset<int>::iterator umit;

//  Utility function to print unordered_multiset
void printUset(unordered_multiset<int> ums)
{
    // begin() returns iterator to first element of
    // set
    umit it = ums.begin();
    for (; it != ums.end(); it++)
        cout << *it << " ";
    cout << endl;
}

//  function to delete one copy of val from set
void erase_one_entry(unordered_multiset<int>& ums,
                    int val)
{
    //  find returns iterator to first position
    umit it = ums.find(val);

    //  if element is there then erasing that
    if (it != ums.end())
       ums.erase(it);
}

//  Driver program to check above function
int main()
{
    //  initializing multiset by initializer list
    unordered_multiset<int> ums ({1, 3, 1, 7, 2, 3,
                                 4, 1, 6});

    int val = 1;
    printUset(ums);
    erase_one_entry(ums, val);
    printUset(ums);
}
```

输出：

```cpp
6 4 2 7 3 3 1 1 1 
6 4 2 7 3 3 1 1 
```

**无序多集方法：**

*   [`insert()`](https://www.geeksforgeeks.org/unordered_multiset-insert-in-c-stl/) – 在无序多集合中插入新元素。因此增加了容器的尺寸。
*   [`begin()`](https://www.geeksforgeeks.org/unordered_multiset-begin-function-in-c-stl/) – 返回一个迭代器，该迭代器指向容器中的第一个元素或其存储桶中的第一个元素。
*   [`end()`](https://www.geeksforgeeks.org/unordered_multiset-end-function-in-c-stl/) – 返回一个迭代器，该迭代器指向容器中最后一个元素之后的位置，或者指向其存储桶中最后一个元素之后的位置。
*   [`empty()`](https://www.geeksforgeeks.org/unordered_multiset-empty-function-in-cstl/) – 如果无序多集容器为空，则返回 `true`。否则，它返回 `false`。
*   [`find()`](https://www.geeksforgeeks.org/unordered_multiset-find-function-in-cstl/) – 返回一个迭代器，该迭代器指向具有元素 `val` 的位置。
*   [`cbegin()`](https://www.geeksforgeeks.org/unordered_multiset-cbegin-function-in-c-stl/) – 返回指向容器中第一个元素或其存储桶中第一个元素的常量迭代器。
*   [`cend()`](https://www.geeksforgeeks.org/unordered_multiset-cend-function-in-c-stl/) – 返回一个常量迭代器，该迭代器指向容器中最后一个元素之后的位置，或者指向其存储桶中最后一个元素之后的位置。
*   [`equal_range()`](https://www.geeksforgeeks.org/unordered_multiset-equal_range-function-in-cstl/) – 返回所有元素等于给定值的范围。
*   [`emplace()`](https://www.geeksforgeeks.org/unordered_multiset-emplace-function-in-c-stl/) – 在无序多集容器中插入新元素。
*   [`clear()`](https://www.geeksforgeeks.org/unordered_multiset-clear-function-in-c-stl/) – 清除无序多集容器的内容。
*   [`count()`](https://www.geeksforgeeks.org/unordered_multiset-count-function-in-c-stl/) – 返回无序多集容器中等于给定值的元素计数。
*   [`size()`](https://www.geeksforgeeks.org/unordered_multiset-size-in-c-stl/) – `unordered_multiset` 的 `size()` 方法用于统计调用它的 `unordered_set` 的元素个数。
*   [`max_size()`](https://www.geeksforgeeks.org/unordered_multiset-max_size-in-c-stl/) – 无序多集的 `max_size()` 取无序多集容器能够容纳的最大元素数。
*   [`swap()`](https://www.geeksforgeeks.org/unordered_multiset-swap-function-in-c-stl/) – 交换两个无序多集容器的内容。
*   [`erase()`](https://www.geeksforgeeks.org/unordered_multiset-erase-function-in-c-stl/) – 用于移除单个元素或具有确定值的所有元素，或从开始(包括)到结束(不包括)的一系列元素。
*   [`bucket()`](https://www.geeksforgeeks.org/unordered_multiset-bucket-function-in-c-stl/) – 返回给定元素所在的桶号。桶大小从 `0` 到 `bucket_count-1` 不等。
*   [`bucket_size()`](https://www.geeksforgeeks.org/unordered_multiset-bucket_size-function-in-c-stl/) – 返回包含元素 `val` 的存储桶中的元素数量。
*   [`reserve()`](https://www.geeksforgeeks.org/unordered_multiset-reserve-in-c-stl/) – `unordered_multiset` 的 `reserve()` 函数将容器中的桶数(`bucket_count`)设置为最适合包含至少 `n` 个元素。
*   [`max_bucket_count()`](https://www.geeksforgeeks.org/unordered_multiset-max_bucket_count-function-in-c-stl/) – 返回无序多集容器可以拥有的最大桶数。
*   [`load_factor()`](https://www.geeksforgeeks.org/unordered_multiset-load_factor-function-in-c-stl/) – 返回无序多集容器中的当前加载因子。
*   [`max_load_factor()`](https://www.geeksforgeeks.org/unordered_multiset-max_load_factor-in-c-stl/) – 返回无序多集容器的最大加载因子。
*   [`bucket_count()`](https://www.geeksforgeeks.org/unordered_multiset-bucket_count-function-in-c-stl/) – 返回无序多集容器中的存储桶总数。
*   [`hash_function()`](https://www.geeksforgeeks.org/unordered_multiset-hash_function-function-in-c-stl/) – 该哈希函数是一元函数，只接受一个参数，并根据该参数返回 `size_t` 类型的唯一值。
*   [`rehash()`](https://www.geeksforgeeks.org/unordered_multiset-rehash-function-in-c-stl/) – 将容器中的桶数量设置为 `N` 或更多。
*   [`key_eq()`](https://www.geeksforgeeks.org/unordered_multiset-key_eq-function-in-c-stl/) – 根据比较结果返回布尔值。
*   [`emplace_hint()`](https://www.geeksforgeeks.org/unordered_multiset-emplace_hint-function-in-c-stl/) – 在无序多集容器中插入新元素。
*   [`get_allocator()`](https://www.geeksforgeeks.org/unordered_multiset-get_allocator-in-c-stl/) – 该函数获取存储的分配器对象，并返回用于构造容器的分配器对象。
*   [`operator=`](https://www.geeksforgeeks.org/unordered_multiset-operator-in-c-stl/) – 运算符 `=` 是 C++ STL 中的一个运算符，它将一个无序多集复制(或移动)到另一个无序多集，而 `unordered_multiset::operator=` 是对应的运算符函数。

[**最近关于无序多集的文章**](https://www.geeksforgeeks.org/tag/cpp-unordered_multiset/)
本文由乌卡什·特里维迪供稿。如果您发现任何不正确的地方，请写评论，或者您想分享更多关于上面讨论的主题的信息