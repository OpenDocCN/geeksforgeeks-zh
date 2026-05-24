# c++ STL 的 Map 和 Multimap 中的降序

> 原文:[https://www . geesforgeks . org/降序-map-multimap-c-stl/](https://www.geeksforgeeks.org/descending-order-map-multimap-c-stl/)

我们已经讨论了 C++ STL 中的[映射](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)和 C++ STL 中的[多映射](https://www.geeksforgeeks.org/multimap-associative-containers-the-c-standard-template-library-stl/)。这些数据结构的默认行为是以升序存储元素。在 map 和 multimap 中插入元素时如何保证逆序或降序？

想法是当 map/multimap 的一个实例。

**地图中降序:**
地图存储键值对。一个自平衡的 BST(通常是红黑树)被用来实现它。

示例:

```cpp
Input :  (10, "queen"), (20, "rose"),  (5," lion")
Output : (20, "rose"),  (10, "queen"), (5," lion")

```

```cpp
// C++ program makes a map to store
// elements in descending order.
#include<bits/stdc++.h>
using namespace std;

int main()
{
    // Here if greater<int> is used to make
    // sure that elements are stored in
    // descending order of keys.
    map<int, string, greater <int> > mymap;

    // Inserting the elements one by one
    mymap.insert(make_pair(10, "queen"));
    mymap.insert(make_pair(20, "rose"));
    mymap.insert(make_pair(5," lion"));

    // begin() returns to the first value of map.
    map<int,string> :: iterator it;
    for (it=mymap.begin() ; it!=mymap.end() ; it++)
        cout << "(" << (*it).first << ", "
             << (*it).second << ")" << endl;

    return 0;
}
```

输出:

```cpp
(20, rose)
(10, queen)
(5,  lion)

```

**多地图中的降序:**
多地图类似于地图，只是多元素可以有相同的键。在这种情况下，键值和映射值对必须是唯一的，而不是每个元素都是唯一的。示例:

```cpp
Input :  (10, "queen"), (20, "rose"),  (5," lion"), 
         (20, "van"), (20, "watch"), (5, "joker")
Output : (20, rose), (20, van), (20, watch), 
         (10, queen), (5,  lion), (5, joker)
```

```cpp
// C++ program makes a multimap to store
// elements in descending order.
#include<bits/stdc++.h>
using namespace std;

int main()
{
    // Here if greater<int> is used to make
    // sure that elements are stored in
    // descending order of keys.
    multimap<int, string, greater <int> > mymap;

    // Inserting the elements one by one
    mymap.insert(make_pair(10, "queen"));
    mymap.insert(make_pair(20, "rose"));
    mymap.insert(make_pair(5," lion"));
    mymap.insert(make_pair(20, "van")); // Duplicates allowed
    mymap.insert(make_pair(20, "watch"));
    mymap.insert(make_pair(5,"joker"));

    // begin() returns to the first value of multimap.
    multimap<int,string> :: iterator it;
    for (it=mymap.begin() ; it!=mymap.end() ; it++)
        cout << "(" << (*it).first << ", "
             << (*it).second << ")" << endl;

    return 0;
}
```

输出:

```cpp
(20, rose)
(20, van)
(20, watch)
(10, queen)
(5,  lion)
(5, joker)
```

本文由 **Jatin Goyal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。