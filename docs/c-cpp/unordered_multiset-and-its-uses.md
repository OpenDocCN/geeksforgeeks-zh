# 无序 _ 多集及其用途

> 原文:[https://www . geesforgeks . org/无序 _ 多集及其用途/](https://www.geeksforgeeks.org/unordered_multiset-and-its-uses/)

我们在之前的文章中已经讨论过[无序 _ 集合](https://www.geeksforgeeks.org/unorderd_set-stl-uses/)无序 _ 集合的问题是，在该数据结构中不可能存储重复的条目。例如，如果我们有一些值 v 已经在无序 _ 集中，再次插入 v 将没有效果。
为了处理这种复制，应该使用无序多集，它也可以存储重复的元素。在内部，当插入现有值时，数据结构会增加与每个值相关联的计数。由于每个值的计数都存储在无序多集合中，因此它比无序集合占用更多的空间(如果所有值都不同)。
无序 _ 多集的内部实现与无序 _ 集相同，也使用哈希表进行搜索，只是计数值与前一个中的每个值相关联。由于元素的散列，它没有存储元素的特定顺序，所以所有元素可以以任何顺序出现，但是重复的元素会出现在一起。无序多集上的所有操作平均需要恒定的时间，但在最坏的情况下可以达到线性。
无序多集支持许多功能，如下代码所示:

## C

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
    //  begin() returns iterator to first element of set
    umit it = ums.begin();
    for (; it != ums.end(); it++)
        cout << *it << " ";
    cout << endl;
}

//  Driver program to check all function
int main()
{
    //  empty initialization
    unordered_multiset<int> ums1;

    //  Initialization by intializer list
    unordered_multiset<int> ums2 ({1, 3, 1, 7, 2, 3,
                                   4, 1, 6});

    //  Initialization by assignment
    ums1 = {2, 7, 2, 5, 0, 3, 7, 5};

    //  empty() function return true if set is empty
    // otherwise false
    if (ums1.empty())
        cout << "unordered multiset 1 is empty\n";
    else
        cout << "unordered multiset 1 is not empty\n";

    //  size() function returns total number of elements
    // in data structure
    cout << "The size of unordered multiset 2 is : "
         << ums2.size() << endl;

    printUset(ums1);

    ums1.insert(7);

    printUset(ums1);

    int val = 3;

    // find function returns iterator to first position
    // of  val, if exist otherwise it returns iterator
    // to end
    if (ums1.find(val) != ums1.end())
        cout << "unordered multiset 1 contains "
             << val << endl;
    else
        cout << "unordered multiset 1 does not contains "
             << val << endl;

    //  count function returns total number of occurrence in set
    val = 5;
    int cnt = ums1.count(val);
    cout << val << " appears " << cnt
         << " times in unordered multiset 1 \n";

    val = 9;

    //  if count return >0 value then element exist otherwise not
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

输出:

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

正如我们所看到的，大多数操作工作类似于无序 _ 集合的工作，但是需要注意的是:
equal_range(val)函数返回一对类型，其中第一个迭代器指向 val 的第一个位置，第二个迭代器指向数据结构中 val 的最后一个位置。
erase(val)函数从数据结构中删除其所有实例，例如，如果某个值 v 在 unordered_multiset 中出现了 t 次，并且在调用 erase 时，v 被完全删除，这不是多次预期的行为。
我们可以使用 find 函数和迭代器版本的 erase 只删除某个值的一个副本，由于 find 函数将迭代器返回到找到的值的第一个位置，我们可以将这个迭代器传递给 erase 而不是实际值来只删除一个副本，这样做的代码如下所示:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
//  C++ program to delete one copy from unordered set
#include <bits/stdc++.h>
using namespace std;

//  making typedef for short declaration
typedef unordered_multiset<int>::iterator umit;

//  Utility function to print unordered_multiset
void printUset(unordered_multiset<int> ums)
{
    // begin() returns iterator to first element of
    // set
    umit it = ums.begin();
    for (; it != ums.end(); it++)
        cout << *it << " ";
    cout << endl;
}

//  function to delete one copy of val from set
void erase_one_entry(unordered_multiset<int>& ums,
                    int val)
{
    //  find returns iterator to first position
    umit it = ums.find(val);

    //  if element is there then erasing that
    if (it != ums.end())
       ums.erase(it);
}

//  Driver program to check above function
int main()
{
    //  initializing multiset by initializer list
    unordered_multiset<int> ums ({1, 3, 1, 7, 2, 3,
                                 4, 1, 6});

    int val = 1;
    printUset(ums);
    erase_one_entry(ums, val);
    printUset(ums);
}
```

输出:

```cpp
6 4 2 7 3 3 1 1 1 
6 4 2 7 3 3 1 1 
```

**无序 _ 多集方法:**

*   [插入()](https://www.geeksforgeeks.org/unordered_multiset-insert-in-c-stl/)–在无序 _ 多集合中插入新元素。因此增加了容器的尺寸。
*   [begin()](https://www.geeksforgeeks.org/unordered_multiset-begin-function-in-c-stl/)–返回一个迭代器，该迭代器指向容器中的第一个元素或其存储桶中的第一个元素。
*   [end()](https://www.geeksforgeeks.org/unordered_multiset-end-function-in-c-stl/)–返回一个迭代器，该迭代器指向容器中最后一个元素之后的位置，或者指向其存储桶中最后一个元素之后的位置。
*   [empty()](https://www.geeksforgeeks.org/unordered_multiset-empty-function-in-cstl/)–如果无序 _ 多集容器为空，则返回 true。否则，它返回 false。
*   [find()](https://www.geeksforgeeks.org/unordered_multiset-find-function-in-cstl/)–返回一个迭代器，该迭代器指向具有元素 val 的位置。
*   [CBE gin()](https://www.geeksforgeeks.org/unordered_multiset-cbegin-function-in-c-stl/)–返回指向容器中第一个元素或其存储桶中第一个元素的常量迭代器。
*   [cend()](https://www.geeksforgeeks.org/unordered_multiset-cend-function-in-c-stl/)–返回一个常量迭代器，该迭代器指向容器中最后一个元素之后的位置，或者指向其存储桶中最后一个元素之后的位置。
*   [equal _ range()](https://www.geeksforgeeks.org/unordered_multiset-equal_range-function-in-cstl/)–返回所有元素等于给定值的范围。
*   [侵位()](https://www.geeksforgeeks.org/unordered_multiset-emplace-function-in-c-stl/)–在无序多集容器中插入新元素。
*   [清除()](https://www.geeksforgeeks.org/unordered_multiset-clear-function-in-c-stl/)–清除无序多集容器的内容。
*   [count()](https://www.geeksforgeeks.org/unordered_multiset-count-function-in-c-stl/)–返回无序 _ 多集容器中等于给定值的元素计数。
*   [size()](https://www.geeksforgeeks.org/unordered_multiset-size-in-c-stl/)–unordered _ multiset 的 size()方法用于统计调用它的 unordered_set 的元素个数。
*   [max_size](https://www.geeksforgeeks.org/unordered_multiset-max_size-in-c-stl/)–无序多集的 max _ size()取无序多集容器能够容纳的最大元素数。
*   [交换()](https://www.geeksforgeeks.org/unordered_multiset-swap-function-in-c-stl/)–交换两个无序 _ 多集容器的内容。
*   [erase()](https://www.geeksforgeeks.org/unordered_multiset-erase-function-in-c-stl/)–用于移除单个元素或具有确定值的所有元素，或从开始(包括)到结束(不包括)的一系列元素。
*   [桶()](https://www.geeksforgeeks.org/unordered_multiset-bucket-function-in-c-stl/)–返回给定元素所在的桶号。桶大小从 0 到桶计数-1 不等。
*   [bucket _ size()](https://www.geeksforgeeks.org/unordered_multiset-bucket_size-function-in-c-stl/)–返回包含元素 val 的存储桶中的元素数量。
*   [reserve()](https://www.geeksforgeeks.org/unordered_multiset-reserve-in-c-stl/)–unordered _ multiset 的 reverse()函数将容器中的桶数(bucket_count)设置为最适合包含至少 n 个元素。
*   [max _ bucket _ count()](https://www.geeksforgeeks.org/unordered_multiset-max_bucket_count-function-in-c-stl/)–返回无序多集容器可以拥有的最大桶数。
*   [load _ factor()](https://www.geeksforgeeks.org/unordered_multiset-load_factor-function-in-c-stl/)–返回无序多集容器中的当前加载因子。
*   [max _ load _ factor()](https://www.geeksforgeeks.org/unordered_multiset-max_load_factor-in-c-stl/)–返回无序多集容器的最大加载因子。
*   [bucket _ count()](https://www.geeksforgeeks.org/unordered_multiset-bucket_count-function-in-c-stl/)–返回无序多集容器中的存储桶总数。
*   [hash _ function()](https://www.geeksforgeeks.org/unordered_multiset-hash_function-function-in-c-stl/)–该 hash 函数是一元函数，只接受一个参数，并根据该参数返回 size_t 类型的唯一值。
*   [重新灰化()](https://www.geeksforgeeks.org/unordered_multiset-rehash-function-in-c-stl/)–将容器中的铲斗数量设置为 N 或更多。
*   [key _ eq()](https://www.geeksforgeeks.org/unordered_multiset-key_eq-function-in-c-stl/)–根据比较结果返回布尔值。
*   [侵位 _ 提示()](https://www.geeksforgeeks.org/unordered_multiset-emplace_hint-function-in-c-stl/)–在无序 _ 多集容器中插入新元素。
*   [get _ 分配器](https://www.geeksforgeeks.org/unordered_multiset-get_allocator-in-c-stl/)–该函数获取存储的分配器对象，并返回用于构造容器的分配器对象。
*   [运算符=](https://www.geeksforgeeks.org/unordered_multiset-operator-in-c-stl/)–运算符“=”是 C++ STL 中的一个运算符，它将一个无序 _ 多集复制(或移动)到另一个无序 _ 多集，而无序 _ 多集::运算符=是对应的运算符函数。

[**最近关于无序 _ 多集的文章**](https://www.geeksforgeeks.org/tag/cpp-unordered_multiset/)
本文由乌卡什·特里维迪供稿。如果您发现任何不正确的地方，请写评论，或者您想分享更多关于上面讨论的主题的信息