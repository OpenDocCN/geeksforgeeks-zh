# 查询插入、删除一个数字的一个出现，并打印最少和最频繁的元素

> 原文:[https://www . geesforgeks . org/query-to-insert-delete-one-occurrence-of-number-and-print-最少和最频繁出现的元素/](https://www.geeksforgeeks.org/queries-to-insert-delete-one-occurrence-of-a-number-and-print-the-least-and-most-frequent-element/)

给定如下所述的类型 1、2、3 和 4 的 Q 个查询。

*   **键入-1:** 在列表中插入一个数字。
*   **类型-2:** 如果存在，只删除一个数字的一次出现。
*   **Type-3:** 打印最不频繁的元素，如果存在多个元素，则打印其中最大的。
*   **Type-4:** 打印最频繁的元素，如果存在多个元素，则打印其中最小的元素。

任务是编写一个程序来执行上述所有查询。
**例:**

> **输入:**
> 查询 1: 1 6
> 查询 2: 1 6
> 查询 3: 1 7
> 查询 4: 3
> 查询 5: 1 7
> 查询 6: 2 7
> 查询 7: 1 7
> 查询 8: 3
> 查询 9: 4
> **输出:**
> 7
> 7
> 6
> 回答查询 4 时，查询的频率
> 在 Query8 中，最不频繁的元素是 6 和 7，所以打印最大的。
> 在 Query9 中，最常出现的元素是 6 和 7，所以打印最小的。

一种简单的方法是使用任何数据结构(数组，向量，..)并储存所有元素。使用[散列表](https://www.geeksforgeeks.org/hashing-data-structure/)，可以存储每个元素的频率。在处理类型-2 的查询时，从存储该元素的数据存储区中删除该元素的一个匹配项。类型 3 和类型 4 的查询可以通过遍历哈希表来回答。每个查询的时间复杂度将是 **O(N)** ，其中 N 是在此之前 DS 中的元素数量。
一种**有效的方法**是使用[设置](https://www.geeksforgeeks.org/set-in-cpp-stl/)容器来回答每个查询。使用两个集合，一个散列表，上述问题可以在每个查询的**0(log n)**中解决。使用两套 *s1* 和 *s2* ，一套存储 ***{num，frequency}*** ，另一套存储 ***{frequency，number}*** 。使用存储每个数字的频率的散列图。使用运算符重载设计集合 s2，使其按照第一个元素的升序排序。如果第一个元素看起来与一个或多个元素相同，则集合将按第二个元素的降序排序。用户定义的[操作-过载](https://www.geeksforgeeks.org/operator-overloading-c/)功能将是:

```cpp
bool operator<(pr a, pr b) {
 if(a.first == b.first) return a.second > b.second;          
 return a.first < b.first;
}
Note: Operator overloading only works with user-defined 
data-types. *pr* is a struct which has first and second as two integers. 
```

下面是求解每种类型查询的算法:

*   **类型 1:** 使用哈希表检查元素是否存在。如果不存在，则在[哈希表](https://www.geeksforgeeks.org/hashing-set-1-introduction/)中标记该数字。使用[插入()](https://www.geeksforgeeks.org/set-insert-function-in-c-stl/)将 **{num，1}** 插入器械包 s1，将**{ num }**插入器械包 2。如果之前存在，则从哈希表中获取频率，并使用 [find()](https://www.geeksforgeeks.org/set-find-function-in-c-stl/) 和 [erase()](https://www.geeksforgeeks.org/seterase-c-stl/) 功能从 set1 中删除 **{num，frequency}** ，从 set2 中删除 **{frequency，num}** 。在集合 1 中插入 **{num，frequency+1}** ，在集合 2 中插入 **{frequency+1，num}** 。另外，增加哈希表中的计数。
*   **类型 2:** 在查询类型 1 中遵循与上面相同的过程。唯一不同的是减少哈希表中的计数，在集合 1 中插入 **{num，frequency-1}** ，在集合 2 中插入 **{frequency-1，num}** 。
*   **类型 3:** 打印可以使用 begin()函数获得的开始元素，因为集合的设计方式是 [begin()](https://www.geeksforgeeks.org/setbegin-setend-c-stl/) 返回最不频繁的元素。如果有多个，则返回最大的。
*   **类型 4:** 打印集合中的最后一个元素，可以使用集合中的 [rbegin()](https://www.geeksforgeeks.org/setrbegin-and-setrend-in-c-stl/) 功能获得。

以下是上述方法的实现:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program for performing
// Queries of insert, delete one
//  occurrence of a number and
// print the least and most frequent element
#include <bits/stdc++.h>
using namespace std;

// user-defined data-types
struct pr {
    int first;
    int second;
};

// user-defined function to
// design a set
bool operator<(pr a, pr b)
{
    if (a.first == b.first)
        return a.second > b.second;
    return a.first < b.first;
}

// declare a user-defined set
set<pr> s1, s2;

// hash map
unordered_map<int, int> m;

// Function to process the query
// of type-1
void type1(int num)
{

    // if the element is already there
    if (m[num]) {

        // get the frequency of the element
        int cnt = m[num];

        // returns an iterator pointing to
        // position where the pair is
        auto it1 = s1.find({ num, cnt });
        auto it2 = s2.find({ cnt, num });

        // deletes the pair from sets
        s1.erase(it1);
        s2.erase(it2);

        // re-insert the pair by increasing
        // frequency
        s1.insert({ num, m[num] + 1 });
        s2.insert({ m[num] + 1, num });
    }

    // if the element is not there in the list
    else {

        // insert the element with frequency 1
        s1.insert({ num, 1 });
        s2.insert({ 1, num });
    }

    // increase the count in hash-table
    m[num] += 1;
}

// Function to process the query
// of type-2
void type2(int num)
{
    // if the element exists
    if (m[num]) {

        // get the frequency of the element
        int cnt = m[num];

        // returns an iterator pointing to
        // position where the pair is
        auto it1 = s1.find({ num, cnt });
        auto it2 = s2.find({ cnt, num });

        // deletes the pair from sets
        s1.erase(it1);
        s2.erase(it2);

        // re-insert the pair by increasing
        // frequency
        s1.insert({ num, m[num] - 1 });
        s2.insert({ m[num] - 1, num });

        // decrease the count
        m[num] -= 1;
    }
}

// Function to process the query
// of type-3
int type3()
{
    // if the set is not empty
    // return the first element
    if (!s1.empty()) {
        auto it = s2.begin();
        return it->second;
    }

    else
        return -1;
}

// Function to process the query
// of type-4
int type4()
{

    // if the set is not empty
    // return the last element
    if (!s1.empty()) {
        auto it = s2.rbegin();
        return it->second;
    }

    else
        return -1;
}
// Driver Code
int main()
{

    // Queries

    // inserts 6, 6 and 7
    type1(6);
    type1(6);
    type1(7);

    // print the answer to query of type3
    cout << type3() << endl;

    // inserts 7
    type1(7);

    // deletes one occurrence of 7
    type2(7);

    // inserts 7
    type1(7);

    // print the answer to query of type3
    cout << type3() << endl;

    // print the answer to query of type4
    cout << type4() << endl;

    return 0;
}
```

**Output:** 

```cpp
7
7
6
```

**时间复杂度:**每个查询 O(log N)。
**辅助空间:** O(N)