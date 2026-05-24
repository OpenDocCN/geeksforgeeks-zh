# 无序 _ 多映射及其应用

> 原文:[https://www . geesforgeks . org/unordered _ multimap-and-its-application/](https://www.geeksforgeeks.org/unordered_multimap-and-its-application/)

**允许重复:**
我们已经在[之前的帖子](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/)中讨论了无序 _map，但是有一个限制，我们不能在无序 _map 中存储重复，也就是说，如果我们的无序 _multimap 中已经有一个键值对，并且插入了另一个键值对，那么两个键值对都会在那里，而在无序 _map 的情况下，对应于键值的先前值会被只会在那里的新值更新。甚至可以在无序 _multimap 中存在两次。

**内部表示:**
无序 _multimap 的内部实现与无序 _map 的内部实现相同，但是对于重复的键，每个键值对维护另一个计数值。由于对存储在哈希表中，它们之间没有特定的顺序，但是具有相同键的对在数据结构中聚集在一起，而具有相同值的对不能保证聚集在一起。

**时间复杂度:**
无序 _ 多 map 上的所有操作平均花费恒定的时间量，但是在最坏的情况下，时间可能会变成线性的，这取决于内部使用的哈希函数，但是从长远来看，无序 _ 多 map 优于多 map(基于树的多 map)。

**函数:**
无序 _ 多映射支持许多函数，如下代码所示:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate various function of
// unordered_multimap
#include <bits/stdc++.h>
using namespace std;

// making typedef for short declaration
typedef unordered_multimap<string, int>::iterator umit;

// Utility function to print unordered_multimap
void printUmm(unordered_multimap<string, int> umm)
{
    // begin() returns iterator to first element of map
    umit it = umm.begin();

    for (; it != umm.end(); it++)
        cout << "<" << it->first << ", " << it->second
             << ">  ";

    cout << endl;
}

// Driver code
int main()
{
    // empty initialization
    unordered_multimap<string, int> umm1;

    // Initialization bu intializer list
    unordered_multimap<string, int> umm2(
        { { "apple", 1 },
          { "ball", 2 },
          { "apple", 10 },
          { "cat", 7 },
          { "dog", 9 },
          { "cat", 6 },
          { "apple", 1 } });

    // Initialization by assignment operation
    umm1 = umm2;
    printUmm(umm1);

    // empty returns true, if container is empty else it
    // returns false
    if (umm2.empty())
        cout << "unordered multimap 2 is empty\n";
    else
        cout << "unordered multimap 2 is not empty\n";

    // size returns total number of elements in container
    cout << "Size of unordered multimap 1 is "
         << umm1.size() << endl;

    string key = "apple";

    // find and return any pair, associated with key
    umit it = umm1.find(key);
    if (it != umm1.end()) {
        cout << "\nkey " << key << " is there in unordered "
             << " multimap 1\n";
        cout << "\none of the value associated with " << key
             << " is " << it->second << endl;
    }
    else
        cout << "\nkey " << key
             << " is not there in unordered"
             << " multimap 1\n";

    // count returns count of total number of pair
    // associated with key
    int cnt = umm1.count(key);
    cout << "\ntotal values associated with " << key
         << " are " << cnt << "\n\n";

    printUmm(umm2);

    // one insertion by making pair explicitly
    umm2.insert(make_pair("dog", 11));

    // insertion by initializer list
    umm2.insert({ { "alpha", 12 }, { "beta", 33 } });
    cout << "\nAfter insertion of <apple, 12> and <beta, "
            "33>\n";
    printUmm(umm2);

    // erase deletes all pairs corresponding to key
    umm2.erase("apple");
    cout << "\nAfter deletion of apple\n";
    printUmm(umm2);

    // clear deletes all pairs from container
    umm1.clear();
    umm2.clear();

    if (umm2.empty())
        cout << "\nunordered multimap 2 is empty\n";
    else
        cout << "\nunordered multimap 2 is not empty\n";
}
```

**Output**

```cpp
<dog, 9>  <cat, 6>  <cat, 7>  <ball, 2>  <apple, 1>  <apple, 10>  <apple, 1>  
unordered multimap 2 is not empty
Size of unordered multimap 1 is 7

key apple is there in unordered  multimap 1

one of the value associated with apple is 1

total values associated with apple are 3

<dog, 9>  <cat, 6>  <cat, 7>  <ball, 2>  <apple, 1>  <apple, 10>  <apple, 1>  

After insertion of <apple, 12> and <beta, 33>
<alpha, 12>  <dog, 11>  <dog, 9>  <beta, 33>  <cat, 6>  <cat, 7>  <ball, 2>  <apple, 1>  <apple, 10>  <apple, 1>  

After deletion of apple
<alpha, 12>  <dog, 11>  <dog, 9>  <beta, 33>  <cat, 6>  <cat, 7>  <ball, 2>  

unordered multimap 2 is empty
```

正如我们在上面的代码中看到的，大部分操作工作类似于无序 _map，但是需要注意的是:
我们可以使用初始化器列表一次初始化并插入许多对。
无序 _ 多映射没有[]运算符，因为对应于一个键的值不是唯一的，一个键可以有许多值，因此[]运算符不能应用于它们。
擦除功能删除与所提供的键相关联的值的所有实例。
Find 函数返回一个迭代器，该迭代器指向与该键相关联的所有键-值对的任何实例。

**如果某个键有特定值，如何访问/删除？**
如果我们想检查一个特定的是否存在，我们需要遍历所有与 k 对应的键值对，以类似的方式我们可以从数据结构中删除一个特定的副本。没有指定键的所有值的存储顺序。

## C++

```cpp
// C++ program to implement find and erase for specific
// key-value pair for unordered_multimap
#include <bits/stdc++.h>
using namespace std;

// making typedef for short declaration
typedef unordered_multimap<string, int>::iterator umit;

// function to check whether p is there in map or not
bool find_kv(unordered_multimap<string, int>& umm,
             pair<string, int> p)
{
    // equal_range returns pair of iterator of first and
    // last position associated with key
    pair<umit, umit> it = umm.equal_range(p.first);
    umit it1 = it.first;

    pair<string, int> tmp;

    // looping over all values associated with key
    while (it1 != it.second)
    {
        tmp = *it1;
        if (tmp == p)
            return true;
        it1++ ;
    }
    return false;
}

// function to delete one copy of pair p from map umm
void erase_kv(unordered_multimap<string, int>& umm,
              pair<string, int> p)
{
    // equal_range returns pair of iterator of first and
    // last position associated with key
    pair<umit, umit> it = umm.equal_range(p.first);
    umit it1 = it.first;
    pair<string, int> tmp;

    // looping over all values associated with key
    while (it1 != it.second)
    {
        tmp = *it1;
        if (tmp == p)
        {
            // iterator version of erase : deletes pair
            // at that position only
            umm.erase(it1);
            break;
        }
        it1++ ;
    }
}

// Utility function to print unordered_multimap
void printUmm(unordered_multimap<string, int> umm)
{
    // begin() returns iterator to first element of map
    umit it = umm.begin();
    for (; it != umm.end(); it++)
        cout << "<" << it->first << ", " << it->second
             << "> ";
    cout << endl;
}

// Driver code
int main()
{
    // initializing multimap by initializer list
    unordered_multimap<string, int> umm({ { "apple", 1 },
                                          { "ball", 2 },
                                          { "apple", 10 },
                                          { "cat", 7 },
                                          { "dog", 9 },
                                          { "cat", 6 },
                                          { "apple", 1 } });

    cout << "Initial content\n";
    printUmm(umm);
    pair<string, int> kv = make_pair("apple", 1);

    // inserting one more <apple, 1> pair
    umm.insert({ "apple", 1 });
    cout << "\nAfter insertion of one more <apple, 1>\n";
    printUmm(umm);

    if (find_kv(umm, kv))
        erase_kv(umm, kv);
    else
        cout << "key-value pair is not there in unordered "
                "multimap\n";

    cout << "\nAfter deletion one occurrence of <apple, "
            "1>\n";
    printUmm(umm);
}
```

**Output**

```cpp
Initial content
<dog, 9> <cat, 6> <cat, 7> <ball, 2> <apple, 1> <apple, 10> <apple, 1> 

After insertion of one more <apple, 1>
<dog, 9> <cat, 6> <cat, 7> <ball, 2> <apple, 1> <apple, 1> <apple, 10> <apple, 1> 

After deletion one occurrence of <apple, 1>
<dog, 9> <cat, 6> <cat, 7> <ball, 2> <apple, 1> <apple, 10> <apple, 1> 
```

**无序 _ 多映射的方法:**

*   [begin()](https://www.geeksforgeeks.org/unordered_multimap-begin-and-end-function-in-c-stl/)–返回一个迭代器，该迭代器指向容器中的第一个元素或其存储桶中的第一个元素。
*   [end()](https://www.geeksforgeeks.org/unordered_multimap-begin-and-end-function-in-c-stl/)–返回一个迭代器，该迭代器指向容器中最后一个元素之后的位置或其存储桶中最后一个元素之后的位置。
*   [count()](https://www.geeksforgeeks.org/unordered_multimap-count-function-in-c-stl/)–返回容器中键等于参数中传递的键的元素数。
*   [CBE gin()](https://www.geeksforgeeks.org/unordered_multimap-cbegin-function-in-c-stl/)–返回指向容器中第一个元素或其存储桶中第一个元素的常量迭代器。
*   [cend()](https://www.geeksforgeeks.org/unordered_multimap-cend-function-in-c-stl/)–返回一个常量迭代器，该迭代器指向容器中最后一个元素之后的位置或其存储桶中最后一个元素之后的位置。
*   [清除()](https://www.geeksforgeeks.org/unordered_multimap-clear-function-in-c-stl/)–清除无序 _ 多映射容器的内容。
*   [size()](https://www.geeksforgeeks.org/unordered_multimap-size-function-in-c-stl/)–返回无序 _ 多映射的大小。它表示容器中元素的数量。
*   [交换()](https://www.geeksforgeeks.org/unordered_multimap-swap-function-in-c-stl/)–交换两个无序 _ 多映射容器的内容。两个容器的尺寸可以不同。
*   [find()](https://www.geeksforgeeks.org/unordered_multimap-find-function-in-c-stl/)–返回一个迭代器，该迭代器指向具有关键字 k 的元素之一。
*   [bucket _ size()](https://www.geeksforgeeks.org/unordered_multimap-bucket_size-function-in-c-stl/)–返回 bucket 中元素的个数 n。
*   [empty()](https://www.geeksforgeeks.org/unordered_multimap-empty-function-in-c-stl/)–如果无序 _multimap 容器为空，则返回 true。否则，它返回 false。
*   [equal _ range()](https://www.geeksforgeeks.org/unordered_multimap-equal_range-function-in-c-stl/)–返回所有元素的键等于一个键的范围。
*   [操作符=](https://www.geeksforgeeks.org/unordered_multimap-operator-in-c/)–从不同容器复制/分配/移动元素。
*   [max _ size()](https://www.geeksforgeeks.org/unordered_multimap-max_size-function-in-c-stl/)–返回无序多映射容器可以容纳的最大元素数。
*   [load _ factor()](https://www.geeksforgeeks.org/unordered_multimap-load_factor-function-in-c-stl/)–返回无序多映射容器中的当前加载因子。
*   [key _ eq()](https://www.geeksforgeeks.org/unordered_multimap-key_eq-function-in-c-stl/)–根据比较结果返回布尔值。
*   [侵位()](https://www.geeksforgeeks.org/unordered_multimap-emplace-function-in-c-stl/)–在无序 _ 多映射容器中插入一个新的{key，element}。
*   [侵位 _ 提示()](https://www.geeksforgeeks.org/unordered_multimap-emplace_hint-function-in-c-stl/)–在无序 _ 多映射容器中插入一个新的{key:element}。
*   [bucket _ count()](https://www.geeksforgeeks.org/unordered_multimap-bucket_count-function-in-c-stl/)–返回无序多映射容器中的桶总数。
*   [桶()](https://www.geeksforgeeks.org/unordered_multimap-bucket-function-in-c-stl/)–返回给定键所在的桶号。
*   [max _ load _ factor()](https://www.geeksforgeeks.org/unordered_multimap-max_load_factor-function-in-c-stl/)–返回无序 _multimap 容器的最大加载因子。
*   [重新灰化()](https://www.geeksforgeeks.org/unordered_multimap-rehash-function-in-c-stl/)–将容器中的铲斗数量设置为 N 或更多。
*   [reserve()](https://www.geeksforgeeks.org/unordered_multimap-reserve-function-in-c-stl/)–将容器中的桶数(bucket_count)设置为最合适的数量，使其至少包含 n 个元素。
*   [hash _ function()](https://www.geeksforgeeks.org/unordered_multimap-hash_function-in-c-stl/)–该 hash 函数是一元函数，只接受单个参数，并基于该参数返回 size_t 类型的唯一值。
*   [max _ bucket _ count()](https://www.geeksforgeeks.org/unordered_multimap-max_bucket_count-function-in-c-stl/)–返回无序多映射容器可以拥有的最大桶数。

[**最近关于无序 _ 多地图的文章**](https://www.geeksforgeeks.org/tag/cpp-unordered_multimap/)
本文由乌卡什·特里维迪供稿。如果您发现任何不正确的地方，或者您想分享关于上面讨论的主题的更多信息，请写评论