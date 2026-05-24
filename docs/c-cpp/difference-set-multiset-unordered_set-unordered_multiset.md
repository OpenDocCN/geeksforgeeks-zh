# 集合、多集合、无序集合、无序多集合之间的区别

> 原文:[https://www . geesforgeks . org/different-set-multist-无序 _ set-无序 _ multist/](https://www.geeksforgeeks.org/difference-set-multiset-unordered_set-unordered_multiset/)

1. **[设置](https://www.geeksforgeeks.org/set-in-cpp-stl/)**
(i)按排序顺序存储值。
(ii)仅存储唯一值。
(iii)元素只能插入或删除，不能修改。
(iv)我们可以通过给出开始迭代器和结束迭代器的位置来删除 1 个以上的元素。
(v)使用迭代器遍历。
(六)套执行为[二叉查找树](https://www.geeksforgeeks.org/binary-search-tree-set-1-search-and-insertion/)。

```cpp
// CPP program to demonstrate insert and 
// delete in set
#include <bits/stdc++.h>
using namespace std;
int main()
{
    // set declare
    set<int> s;

    // Elements added to set
    s.insert(12);
    s.insert(10);
    s.insert(2);
    s.insert(10); // duplicate added
    s.insert(90);
    s.insert(85);
    s.insert(45);

    // Iterator declared to traverse
    // set elements
    set<int>::iterator it, it1, it2;
    cout << "Set elements after sort and "
            "removing duplicates:\n";
    for (it = s.begin(); it != s.end(); it++) 
        cout << *it << ' ';    
    cout << '\n';

    it1 = s.find(10);
    it2 = s.find(90);

    // elements from 10 to elements before
    // 90 erased
    s.erase(it1, it2);
    cout << "Set Elements after erase:\n";
    for (it = s.begin(); it != s.end(); it++)
        cout << *it << ' ';

    return 0;
}
```

```cpp
OUTPUT:
Set elements after sort and removing duplicates:
2 10 12 45 85 90
Set Elements after erase:
2 90

```

2. **[【多集】](https://www.geeksforgeeks.org/multiset-in-cpp-stl/)**
(i)按排序顺序存储元素。
(ii)它允许储存多种元素。
(iii)我们可以通过给出开始迭代器和结束迭代器来删除 1 个以上的元素。
注意:-所有其他类似于 set 的属性。

```cpp
// CPP program to demonstrate insert and 
// delete in set
#include <bits/stdc++.h>
using namespace std;
int main()
{
    // multiset declare
    multiset<int> s;

    // Elements added to set
    s.insert(12);
    s.insert(10);
    s.insert(2);
    s.insert(10); // duplicate added
    s.insert(90);
    s.insert(85);
    s.insert(45);

    // Iterator declared to traverse
    // set elements
    multiset<int>::iterator it, it1, it2;
    cout << "Multiset elements after sort\n";
    for (it = s.begin(); it != s.end(); it++) 
        cout << *it << ' ';    
    cout << '\n';

    it1 = s.find(10);
    it2 = s.find(90);

    // elements from 10 to elements before 90 
    // erased
    s.erase(it1, it2);

    cout << "Multiset Elements after erase:\n";
    for (it = s.begin(); it != s.end(); it++) 
        cout << *it << ' ';    

    return 0;
}
```

```cpp
OUTPUT:
Multiset elements after sort
2 10 10 12 45 85 90
Multiset Elements after erase:
2 90

```

3. **[【无序 _ 集合】](https://www.geeksforgeeks.org/unorderd_set-stl-uses/)**
(i)元素可以任意顺序存储。(无排序顺序)
(ii)仅存储唯一值。
(iii)用于存储元素的哈希表。
(iv)我们只能擦除给定迭代器位置的元素。
注意:-所有其他与 set 相似的属性。

```cpp
// CPP program to demonstrate insert and 
// delete in unordered_set
#include <bits/stdc++.h>
using namespace std;
int main()
{
    // unordered_set declare
    unordered_set<int> s;

    // Elements added to set
    s.insert(12);
    s.insert(10);
    s.insert(2);
    s.insert(10); // duplicate added
    s.insert(90);
    s.insert(85);
    s.insert(45);
    s.insert(12);
    s.insert(70);

    // Iterator declared to traverse
    // set elements
    unordered_set<int>::iterator it, it1;
    cout << "Unordered_set elements after sort:\n";
    for (it = s.begin(); it != s.end(); it++) 
        cout << *it << ' ';
    cout << '\n';

    it1 = s.find(10);

    // element 10 erased
    s.erase(it1);
    cout << "Unoredered_set Elements after erase:\n";
    for (it = s.begin(); it != s.end(); it++) 
         cout << *it << ' ';    

    return 0;
}
```

```cpp
OUTPUT:
Unordered_set elements after sort:
70 85 45 12 10 2 90 
Unoredered_set Elements after erase:
70 85 45 12 2 90 
```

4. **[【无序 _ 多集】](https://www.geeksforgeeks.org/unordered_multiset-and-its-uses/)**
(一)元素可以任意顺序存储。
(ii)可以存储重复元素。
(iii)用于存储元素的哈希表。
(iv)我们只能擦除给定迭代器位置的元素。
注意:-所有其他与 set 相似的属性。

```cpp
// CPP program to demonstrate insert and 
// delete in unordered_multiset
#include <bits/stdc++.h>
using namespace std;
int main()
{
    // unordered_multiset declare
    unordered_multiset<int> s;

    // Elements added to set
    s.insert(12);
    s.insert(10);
    s.insert(2);
    s.insert(10); // duplicate added
    s.insert(90);
    s.insert(85);
    s.insert(45);

    // Iterator declared to traverse
    // set elements
    unordered_multiset<int>::iterator it, it1;
    cout << "Unordered-Multiset elements after sort:\n";
    for (it = s.begin(); it != s.end(); it++)
        cout << *it << ' ';    
    cout << '\n';

    it1 = s.find(10);

    // element 10 trained
    s.erase(it1);

    cout << "Unordered-Multiset Elements after "
            "erase:\n";
    for (it = s.begin(); it != s.end(); it++) 
        cout << *it << ' ';

    return 0;
}
```

```cpp
OUTPUT:
Unordered-Multiset elements after sort:
85 45 12 90 2 10 10 
Unordered-Multiset Elements after erase:
85 45 12 90 2 10 

```

**结论:**
简单来说，**集**是一个存放 ***已排序且唯一的*** 元素的容器。如果添加了 ***【无序】*** ，则表示元素是 ***而不是*** 。如果增加 ***多集*** 表示允许 ***重复元素*** 存储。

本文由 **[SHAURYA UPPAL](https://www.linkedin.com/in/shaurya-uppal-3b7a6373/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。