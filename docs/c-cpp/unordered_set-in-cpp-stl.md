# c++ 标准模板库中的无序集

> 原文:[https://www.geeksforgeeks.org/unordered_set-in-cpp-stl/](https://www.geeksforgeeks.org/unordered_set-in-cpp-stl/)

一个**无序集**是使用一个哈希表实现的，其中关键字被哈希到哈希表的索引中，这样插入总是随机的。对**无序集**的所有操作平均花费恒定时间**0(1)**，在最坏的情况下，这可以达到线性时间**0(n)**，这取决于内部使用的散列函数，但是实际上它们执行得非常好，并且通常提供恒定时间查找操作。
无序集可以包含任何类型的键——预定义的或用户定义的数据结构，但是当我们定义用户定义类型的键时，我们需要指定我们的比较函数，根据该函数将比较哪些键。
**集合 vs 无序集合**
[集合](http://geeksquiz.com/set-associative-containers-the-c-standard-template-library-stl/)是唯一键的有序序列，而无序 _ 集合是键可以以任何顺序存储的集合，因此是无序的。集合被实现为平衡的树结构，这就是为什么可以保持元素之间的顺序(通过特定的树遍历)。集合运算的时间复杂度为 O(log n)，而对于无序 _ 集合，时间复杂度为 O(1)。
**无序集上的方法:**
对于无序集，定义了许多函数，其中最常用的是大小和空容量、查找搜索关键字、插入和擦除修改。
无序集只允许唯一键，对于重复键，应该使用无序多集。
无序 _ 集中的声明、查找、插入和迭代示例如下:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to demonstrate various function of unordered_set
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // declaring set for storing string data-type
    unordered_set <string> stringSet ;

    // inserting various string, same string will be stored
    // once in set

    stringSet.insert("code") ;
    stringSet.insert("in") ;
    stringSet.insert("c++") ;
    stringSet.insert("is") ;
    stringSet.insert("fast") ;

    string key = "slow" ;

    //  find returns end iterator if key is not found,
    //  else it returns iterator to that key

    if (stringSet.find(key) == stringSet.end())
        cout << key << " not found" << endl << endl ;
    else
        cout << "Found " << key << endl << endl ;

    key = "c++";
    if (stringSet.find(key) == stringSet.end())
        cout << key << " not found\n" ;
    else
        cout << "Found " << key << endl ;

    // now iterating over whole set and printing its
    // content
    cout << "\nAll elements : ";
    unordered_set<string> :: iterator itr;
    for (itr = stringSet.begin(); itr != stringSet.end(); itr++)
        cout << (*itr) << endl;
}
```

**输出:**

```cpp
slow not found

Found c++

All elements : 
is
fast
c++
in
code
```

平均而言，查找、插入和擦除需要恒定的时间。如果键不在集合中，find()函数将迭代器返回到 end()，否则返回键位置的迭代器。迭代器充当键值的指针，这样我们就可以通过使用*运算符对键值进行解引用来获取键值。
**一个基于无序集**的实际问题——给定一个整数数组(列表)，找出其中所有的重复项。

```cpp
Input  : arr[] = {1, 5, 2, 1, 4, 3, 1, 7, 2, 8, 9, 5}
Output : Duplicate item are : 5 2 1 
```

下面是使用无序集的 C++ 解决方案。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to find duplicate from an array using
// unordered_set
#include <bits/stdc++.h>
using namespace std;

// Print duplicates in arr[0..n-1] using unordered_set
void printDuplicates(int arr[], int n)
{
    // declaring unordered sets for checking and storing
    // duplicates
    unordered_set<int> intSet;
    unordered_set<int> duplicate;

    // looping through array elements
    for (int i = 0; i < n; i++)
    {
        // if element is not there then insert that
        if (intSet.find(arr[i]) == intSet.end())
            intSet.insert(arr[i]);

        // if element is already there then insert into
        // duplicate set
        else
            duplicate.insert(arr[i]);
    }

    // printing the result
    cout << "Duplicate item are : ";
    unordered_set<int> :: iterator itr;

    // iterator itr loops from begin() till end()
    for (itr = duplicate.begin(); itr != duplicate.end(); itr++)
        cout << *itr << " ";
}

// Driver code
int main()
{
    int arr[] = {1, 5, 2, 1, 4, 3, 1, 7, 2, 8, 9, 5};
    int n = sizeof(arr) / sizeof(int);

    printDuplicates(arr, n);
    return 0;
}
```

**输出:**

```cpp
Duplicate item are : 5 1 2 
```

**无序集的方法:**

*   [Insert()](https://www.geeksforgeeks.org/unordered_set-insert-function-in-c-stl/)–在无序集容器中插入一个新的{element}。
*   [begin()](https://www.geeksforgeeks.org/unordered_set-begin-function-in-c-stl/)–返回指向无序集容器中第一个元素的迭代器。
*   [end()](https://www.geeksforgeeks.org/unordered_set-end-in-c-stl/)–返回指向结束元素的迭代器。
*   [计数()](https://www.geeksforgeeks.org/unordered_set-count-function-in-c-stl/)–计数无序集容器中特定元素的出现次数。
*   [find()](https://www.geeksforgeeks.org/unordered_set-find-function-in-c-stl/)–搜索容器中的元素。
*   [清除()](https://www.geeksforgeeks.org/unoredered_set-clear-function-in-c-stl/)–从无序 _ 集中移除所有元素并清空它。
*   [CBE gin()](https://www.geeksforgeeks.org/unordered_set-cbegin-function-in-c-stl/)–返回指向无序集容器中第一个元素的 const_iterator。
*   [cend()](https://www.geeksforgeeks.org/unordered_set-cend-function-in-c-stl/)–返回一个 const_iterator，指向无序集容器或其中一个桶中的结束元素。
*   [bucket _ size()](https://www.geeksforgeeks.org/unordered_set-bucket_size-in-c-stl/)–返回无序集容器中特定存储桶中存在的元素总数。
*   [擦除()](https://www.geeksforgeeks.org/unordered_set-erase-function-in-c-stl/)–删除单个元素或从开始(包括)到结束(不包括)的一系列元素。
*   [size()](https://www.geeksforgeeks.org/unordered_set-size-function-in-c-stl/)–返回无序集容器中的元素数量。
*   [交换()](https://www.geeksforgeeks.org/unordered_set-swap-function-in-c-stl/)–交换两个无序集容器的值。
*   [放置()](https://www.geeksforgeeks.org/unordered_set-emplace-function-in-c-stl/)–在无序集容器中插入一个元素。
*   [max _ size()](https://www.geeksforgeeks.org/unordered_set-max_size-in-c-stl/)–返回无序集容器可以容纳的最大元素数。
*   [空()](https://www.geeksforgeeks.org/unordered_set-empty-function-in-c-stl/)–检查无序集容器是否为空。
*   [equal _ range](https://www.geeksforgeeks.org/unordered_set-equal_range-in-c-stl/)–返回包含等于给定值的所有元素的范围。
*   [运算符=](https://www.geeksforgeeks.org/unordered_set-operator-in-c-stl/)–将无序 _ 集复制(或移动)到另一个无序 _ 集，无序 _ 集::运算符=是对应的运算符函数。
*   [hash _ function()](https://www.geeksforgeeks.org/unordered_set-hash_function-in-c-stl/)–该 hash 函数是一元函数，只接受一个参数，并根据该参数返回 size_t 类型的唯一值。
*   [reserve()](https://www.geeksforgeeks.org/unordered_set-reserve-function-in-c-stl/)–用于请求无序 _ 集合的容量变化。
*   [桶()](https://www.geeksforgeeks.org/unordered_set-bucket-function-in-c-stl/)–返回特定元素的桶号。
*   [存储桶计数()](https://www.geeksforgeeks.org/unordered_set-bucket_count-function-in-c-stl/)–返回无序集容器中存在的存储桶总数。
*   [加载因子()](https://www.geeksforgeeks.org/unordered_set-load_factor-function-in-c-stl/)–返回无序集容器中的当前加载因子。
*   [rehash()](https://www.geeksforgeeks.org/unordered_set-rehash-function-in-c-stl/)–将 unordered_set 容器中的桶数设置为给定大小或更大。
*   [max _ load _ factor()](https://www.geeksforgeeks.org/unordered_set-max_load_factor-in-c-stl/)–返回(或设置)无序集容器的当前最大加载因子。
*   [侵位 _ 提示()](https://www.geeksforgeeks.org/unordered_set-emplace_hint-function-in-c-stl/)–仅当要插入的值是唯一的，并带有给定的提示时，才在无序 _ 集中插入新元素。
*   [==运算符](https://www.geeksforgeeks.org/unordered_set-operator-in-c-stl-3/)–运算符“==”是 C++ STL 中的一个运算符，在两个无序集和无序集之间执行相等比较运算::运算符==是相同的对应运算符函数。
*   [key _ eq()](https://www.geeksforgeeks.org/unordered_set-key_eq-function-in-c-stl/)–根据比较结果返回布尔值。它返回无序集使用的键等价比较谓词。
*   [符！=](https://www.geeksforgeeks.org/unordered_set-operator-in-c-stl-2/)–该！=是 C++ STL 中的一个关系运算符，用于比较无序集容器之间的等式和不等式。
*   [max _ bucket _ count()](https://www.geeksforgeeks.org/unordered_set-max_bucket_count-function-in-c-stl/)–查找无序 _set 可以拥有的最大桶数。

[最近关于无序 _ 集](https://www.geeksforgeeks.org/tag/cpp-unordered_set/)
的文章本文由[乌卡什·特里维迪](http://qa.geeksforgeeks.org/user/utkarsh111)供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。