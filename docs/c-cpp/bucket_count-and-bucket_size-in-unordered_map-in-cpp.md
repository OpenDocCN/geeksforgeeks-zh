# c++ 中无序映射的桶计数和桶大小

> 原文:[https://www . geesforgeks . org/bucket _ count-and-bucket _ size-in-无序 _map-in-cpp/](https://www.geeksforgeeks.org/bucket_count-and-bucket_size-in-unordered_map-in-cpp/)

正如我们所知，内部[无序 _ 映射](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/)是使用哈希表实现的，因此，桶是内部哈希表中的一个槽，元素根据其键的哈希值被分配给该槽。存储桶的编号从 0 到(存储桶计数-1)。因此，该函数返回桶号，其中带有**键**的元素位于无序地图中。
时间复杂度:O(1)。

**语法:**

```cpp
unordered_map.bucket(k);
k is the key corresponds to which we want to know bucket number.
Returns: The order number of the bucket corresponding to key k.

```

关于铲斗还有两个功能:
**1。std::bucket_count:** 该函数用于统计无序 _ 映射中的 bucket 总数。传递到此函数中不需要任何参数。
时间复杂度:O(1)。

**语法:**

```cpp
unordered_map.bucket_count();
Returns: The number of the bucket present in hash table of unordered_map.

```

**2。std::bucket_size:** 此函数统计无序 _ 映射的每个 bucket 中存在的元素数量。
时间复杂度:桶大小呈线性。

**语法:**

```cpp
unordered_map.bucket_size(i);
where 'i' is the bucket number in which we want 
to find no. of elements. (i < bucket_count)
Returns: The number of elements present in bucket 'i'.

```

```cpp
// C++ program to demonstrate the use of std::bucket
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Declaring umap to be of <string, double> type
    // key will be of string type and mapped value will
    // be of double type
    unordered_map<string, double> umap;

    // inserting values by using [] operator
    umap["PI"] = 3.14;
    umap["root2"] = 1.414;
    umap["log10"] = 2.302;
    umap["loge"] = 1.0;
    umap["e"] = 2.718;

    // Display bucket no. where key, value pair is located
    // using bucket(key)
    for (auto& x : umap) {
        cout << "(" << x.first << ", " << x.second << ")";
        cout << " is in bucket= " 
            << umap.bucket(x.first) << endl;
    }
    cout << endl;

    // Count the no.of buckets in the unordered_map 
    // using bucket_count()
    int n = umap.bucket_count();
    cout << "umap has " << n << " buckets.\n\n";

    // Count no. of elements in each bucket using 
    // bucket_size(position)
    for (int i = 0; i < n; i++) {
        cout << "Bucket " << i << " has " 
             << umap.bucket_size(i) << " elements.\n";
    }

    return 0;
}
```

输出:

```cpp
(PI, 3.14) is in bucket= 5
(e, 2.718) is in bucket= 1
(root2, 1.414) is in bucket= 1
(log10, 2.302) is in bucket= 10
(loge, 1) is in bucket= 7

umap has 11 buckets.

Bucket 0 has 0 elements.
Bucket 1 has 2 elements.
Bucket 2 has 0 elements.
Bucket 3 has 0 elements.
Bucket 4 has 0 elements.
Bucket 5 has 1 elements.
Bucket 6 has 0 elements.
Bucket 7 has 1 elements.
Bucket 8 has 0 elements.
Bucket 9 has 0 elements.
Bucket 10 has 1 elements.

```

我们还可以打印无序映射的每个桶中的所有元素。

```cpp
// C++ program to print all elements present in each bucket
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Declaring umap to be of <string, double> type
    // key will be of string type and mapped value 
    // will be of double type
    unordered_map<string, double> umap;

    // inserting values by using [] operator
    umap["PI"] = 3.14;
    umap["root2"] = 1.414;
    umap["log10"] = 2.302;
    umap["loge"] = 1.0;
    umap["e"] = 2.718;

    unsigned n = umap.bucket_count();

    // Prints elements present in each bucket
    for (unsigned i = 0; i < n; i++) {
        cout << "Bucket " << i << " contains: ";
        for (auto it = umap.begin(i); it != umap.end(i); it++)
            cout << "(" << it->first << ", " 
                 << it->second << ") ";
        cout << "\n";
    }
    return 0;
}
```

输出:

```cpp
Bucket 0 contains: 
Bucket 1 contains: (e, 2.718) (root2, 1.414) 
Bucket 2 contains: 
Bucket 3 contains: 
Bucket 4 contains: 
Bucket 5 contains: (PI, 3.14) 
Bucket 6 contains: 
Bucket 7 contains: (loge, 1) 
Bucket 8 contains: 
Bucket 9 contains: 
Bucket 10 contains: (log10, 2.302) 

```

**bucket 在 std::无序 _map:** 中的使用有多种算法，需要将对象散列到一定数量的 bucket 中，然后处理每个 bucket。比方说，您想要在集合中查找重复项。您散列集合中的所有项目，然后在每个桶中成对比较项目。稍微不那么琐碎的例子是[寻找频繁项目集的 Apriori 算法](https://en.wikipedia.org/wiki/Apriori_algorithm)。

本文由**阿卡什·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。