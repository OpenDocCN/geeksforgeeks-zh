# 删除 `std::map` 中元素的不同方式(`erase()`和`clear()`)

> 原文：[https://www.geeksforgeeks.org/different-ways-delete-elements-stdmap-erase-clear/](https://www.geeksforgeeks.org/different-ways-delete-elements-stdmap-erase-clear/)

本文涉及 `map` 的删除部分。

## 1. 使用 `erase()`

`erase()` 用于删除参数中指定的 `map` 中的键值对，可以按位置、值或一个范围来删除。

### 1.1 擦除(键)
使用参数中提到的键擦除键值对。删除后对 `map` 重新排序。它返回删除的条目数。如果删除不存在的键，则返回 0。
时间复杂度：`log(n)`（`n` 为 `map` 大小）

### 1.2 擦除(iter)
擦除其参数中提到的迭代器所指向的位置处的键值对。
时间复杂度：`log(n)`（`n` 为 `map` 大小）

### 1.3 擦除(`strt_iter`，`end_iter`)
擦除从 `strt_iter` 到 `end_iter` 开始的键值对范围。
时间复杂度：`O(k)`（`k` 为 `map` 大小）

```cpp
// C++ code to demonstrate the working of erase()

#include<iostream>
#include<map> // for map operations
using namespace std;

int main()
{
    // declaring map
    // of char and int
    map< char, int > mp;

    // declaring iterators
    map<char, int>::iterator it ;
    map<char, int>::iterator it1;
    map<char, int>::iterator it2;

    // inserting values 
    mp['a']=5;
    mp['b']=10;
    mp['c']=15;
    mp['d']=20;
    mp['e']=30;

    // printing initial map elements
    cout << "The initial map elements are : \n";

    for (it1 = mp.begin(); it1!=mp.end(); ++ it1)
        cout << it1->first << "->" << it1->second << endl;

    it = mp.begin();

    cout << endl;

    // erasing element using iterator
    // erases 2nd element
    // 'b'
    ++ it;
    mp.erase(it);

    // printing map elements after deletion
    cout << "The map elements after 1st deletion are : \n";

    for (it1 = mp.begin(); it1!=mp.end(); ++ it1)
        cout << it1->first << "->" << it1->second << endl;

    cout << endl;

    // erasing element using value 
    int c = mp.erase('c');

    // printing map elements after deletion
    cout << "The map elements after 2nd deletion are : \n";

    for (it1 = mp.begin(); it1!=mp.end(); ++ it1)
        cout << it1->first << "->" << it1->second << endl;

    cout << "The number of elements deleted in 2nd deletion are : ";
    cout << c << endl;

    cout << endl;

    // erasing element using value 
    // key not present
    int d = mp.erase('w');

    // printing map elements after deletion
    cout << "The map elements after 3rd deletion are : \n";

    for (it1 = mp.begin(); it1!=mp.end(); ++ it1)
        cout << it1->first << "->" << it1->second << endl;

    cout << "The number of elements deleted in 3rd deletion are : ";
    cout << d << endl;

    cout << endl;

    ++ it;
    ++ it;

    // erasing element using range iterator
    // deletes "d" and "e" keys
    mp.erase(it, mp.end());

    // printing map elements 4th deletion
    cout << "The map elements after 4th deletion are : \n";

    for (it1 = mp.begin(); it1!=mp.end(); ++ it1)
        cout << it1->first << "->" << it1->second << endl;

    cout << endl;

}
```

输出：

```cpp
The initial map elements are : 
a->5
b->10
c->15
d->20
e->30

The map elements after 1st deletion are : 
a->5
c->15
d->20
e->30

The map elements after 2nd deletion are : 
a->5
d->20
e->30
The number of elements deleted in 2nd deletion are : 1

The map elements after 3rd deletion are : 
a->5
d->20
e->30
The number of elements deleted in 3rd deletion are : 0

The map elements after 4th deletion are : 
a->5
```

## 2. 使用 `clear()`

此函数清除 `map` 中存在的所有元素。调用此函数后，`map` 的大小变为 0。

```cpp
// C++ code to demonstrate the working of clear()

#include<iostream>
#include<map> // for map operations
using namespace std;

int main()
{
    // declaring map
    // of char and int
    map< char, int > mp;

    // declaring iterator
    map<char, int>::iterator it ;

    // inserting values 
     mp['a']=5;
     mp['b']=10;
     mp['c']=15;
     mp['d']=20;
     mp['e']=30;

    // printing initial map elements
    cout << "The initial map elements are : \n";
    for (it1 = mp.begin(); it1!=mp.end();  ++ it1)
        cout << it1->first << "->" << it1->second << endl;

    // using clear() to erase all elements in map
    mp.clear();

    // printing map elements after deletion
    cout << "The map elements after clearing all elements are : \n";
    for (it1 = mp.begin(); it1!=mp.end();  ++ it1)
        cout << it1->first << "->" << it1->second << endl;

}
```

输出：

```cpp
The initial map elements are : 
a->5
b->10
c->15
d->20
e->30
The map elements after clearing all elements are :
```

本文由 **[【曼吉特·辛格】](https://www.facebook.com/manjeet.04.singh)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 `contribute.geeksforgeeks.org` 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。