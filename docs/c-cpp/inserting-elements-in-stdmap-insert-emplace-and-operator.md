# 在 std::map 中插入元素(插入、定位和操作符[])

> 原文:[https://www . geeksforgeeks . org/inserting-elements-in-stdmap-insert-position-and-operator/](https://www.geeksforgeeks.org/inserting-elements-in-stdmap-insert-emplace-and-operator/)

先决条件:[STL 中的地图](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)

地图是一个容器，顾名思义用来**存储一个键值对**。通过在[**中搜索由“键”定义的**](https://www.geeksforgeeks.org/searching-map-using-stdmap-functions-c/) 【地图】 [**只需要 **O(1)** 的时间复杂度，地图相对于其他容器具有优势，因此在各种编码领域都很有用。本文将讨论插入。**](https://www.geeksforgeeks.org/searching-map-using-stdmap-functions-c/)

**1。使用 insert()** : Insert 函数用于在映射中插入键值对。插入后，元素会重新排序，地图会根据关键字进行排序。

该功能通过 3 种方式实现:

*   **插入(对)**:此功能在地图中插入对。只有当通过的钥匙**不是已经插入的**时，插入才会发生。
    它返回一个指针对。指向已经存在或新插入的对的第一个元素。返回布尔状态“真”或“假”的第二个元素。
    时间复杂度:log(n)，其中 n 是地图的大小
*   **插入(提示，配对)**:在本实现中，**提示指针**与待插入的配对一起发送。使用提示指针是为了帮助 insert()知道实际的插入必须发生在哪里。因此，尝试减少分配配对的时间。
    提示指针不会强制在特定位置插入。该功能**将指针返回到插入线对的位置**。
    时间复杂度:log(n)其中 n 是地图的大小如果提示是最优的那么 **O(1)**
*   **插入(beg_ptr，end_ptr)** :这种类型的插入需要**将其他容器对**插入到地图中。如果重复的对出现在目标容器中，则不会插入它们。
    时间复杂度:k*log(n)其中 n 为地图大小，k 为插入元素个数。

## C++

```cpp
// C++ code to demonstrate the working of insert()

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

    // declaring pair for return value of map containing
    // map iterator and bool
    pair <map<char, int>::iterator, bool> ptr;

    // using insert() to insert single pair
    // inserting 'a' with 20
    ptr = mp.insert( pair<char, int>('a', 20) );

    // checking if the key was already present or newly inserted
    if(ptr.second)
        cout << "The key was newly inserted" ;
    else
        cout << "The key was already present" ;

    cout << endl ;

    // printing map pairs after insertion
    cout << "The map pairs after 1st insertion are : \n";

    for (it1 = mp.begin(); it1!=mp.end(); ++ it1)
        cout << it1->first << "->" << it1->second << endl;

    it = mp.begin();

    // inserting map pair using hint 
    mp.insert(it, pair<char, int>('b', 24) );

    cout << endl ;

    // printing map pairs after insertion
    cout << "The map pairs after 2nd insertion are : \n";

    for (it1 = mp.begin(); it1!=mp.end(); ++ it1)
        cout << it1->first << "->" << it1->second << endl;

    // initializing another map 
    map<char, int> mp2;

    // using insert(beg_iter, end_iter) to copy all elements
    mp2.insert(mp.begin(), mp.end());

    cout << endl ;

    // printing new map pairs after insertion
    cout << "The new map pairs after insertion are : \n";

    for (it1 = mp2.begin(); it1!=mp2.end(); ++ it1)
        cout << it1->first << "->" << it1->second << endl;

}
```

**输出:**

```cpp
The key was newly inserted
The map pairs after 1st insertion are : 
a->20

The map pairs after 2nd insertion are : 
a->20
b->24

The new map pairs after insertion are : 
a->20
b->24
```

**2。使用炮位**:炮位也是用来将对子插入地图的。该功能类似于上面讨论的“insert()”，唯一的区别是**成对的“就地”构造**发生在元素插入的位置，与拷贝或电影现有对象的 insert()相反。

*   **定位()**:使用原地构建策略插入对。将地图的大小增加 1。返回指针对。它的第一个元素是迭代器，指向插入对的位置。2nd 返回一个布尔变量，表示已经存在或新创建的对。
    时间复杂度: **log(n)** (n 为地图大小)
*   **侵位 _ 提示()**:取一个**“提示 _ 迭代器”**得到插入位置的提示，可能会减少插入插入对所需的时间。这不会影响插入的位置。它发生在内部定义的地方。
    时间复杂度: **log(n)** (n 是地图的大小)，如果提示是最优的那么 **O(1)**

## C++

```cpp
// C++ code to demonstrate the working of emplace()
// and emplace_hint()
#include<iostream>
#include<map> // for map operations
using namespace std;

int main()
{
    // declaring map
    map<char, int> mp;

    // declaring iterators
    map<char, int>::iterator it;
    map<char, int>::iterator it1;
    map<char, int>::iterator it2;

    // declaring pair for return value of map containing
    // map iterator and bool
    pair< map<char, int>::iterator, bool> ptr;

    // using emplace() to insert pair element
    // inserting 'a' to 24
    // no "pair" needed, in-place construction
    ptr = mp.emplace('a', 24);

    // checking if the pair was already present or newly inserted
    // returns true. newly inserted
    if (ptr.second)
        cout << "The key was newly inserted" ;
    else
        cout << "The key was already present" ;

    cout << endl;

    // printing map pairs after insertion
    cout << "The map pairs after 1st insertion are : \n";

    for (it1 = mp.begin(); it1!=mp.end(); ++ it1)
        cout << it1->first << "->" << it1->second << endl;

    cout << endl ;

    // using emplace() to insert single pair
    // inserting a to 24 // not inserted this time
    ptr = mp.emplace('a', 24);

    // checking if the key was already present or newly inserted
    // returns false. already inserted
    if(ptr.second)
        cout << "The key was newly inserted" ;
    else
        cout << "The key was already present" ;

    cout << endl ;

    // printing map pairs after insertion
    cout << "The map pairs after 2nd insertion are : \n";

    for (it1 = mp.begin(); it1!=mp.end(); ++ it1)
        cout << it1->first << "->" << it1->second << endl;

    it = mp.begin();

    // inserting map pair using hint
    mp.emplace_hint(it, 'b', 20);

    cout << endl ;

    // printing map pairs after insertion
    cout << "The map pairs after 3rd insertion are : \n";

    for (it1 = mp.begin(); it1!=mp.end(); ++ it1)
        cout << it1->first << "->" << it1->second << endl;

}
```

**输出:**

```cpp
The key was newly inserted
The map pairs after 1st insertion are : 
a->24

The key was already present
The map pairs after 2nd insertion are : 
a->24

The map pairs after 3rd insertion are : 
a->24
b->20
```

**3。使用运算符[]**:“[]”也可用于在地图中插入元素。类似于上面的函数，并返回指向新构造的元素的指针。不同的是，这个运算符**总是构造一个新元素**，也就是说，即使一个值没有映射到一个键，默认构造函数也会被调用，并为该键分配一个“空”值。地图的大小为**总是增加 1** 。
时间复杂度:log(n)，其中 n 是地图的大小

## C++

```cpp
// C++ code to demonstrate the working of operator[]

#include<iostream>
#include<map> // for map operations
using namespace std;

int main()
{
    // declaring map
    map<char, int> mp;

    // using [] to assign key to value
    mp['a'] = 5;
    mp['b'] = 6;
    mp['c'] = 2;

    // printing values
    cout << "The element keys to a is : ";
    cout << mp['a'] << endl;

    cout << "The element keys to b is : ";
    cout << mp['b'] << endl;

    cout << "The element keys to c is : ";
    cout << mp['c'] << endl;

    // default constructor is called
    // prints 0
    cout << "The element keys to d is : ";
    cout << mp['d'] << endl;

}
```

**输出:**

```cpp
The element keys to a is : 5
The element keys to b is : 6
The element keys to c is : 2
The element keys to d is : 0
```

**相关文章** : [在地图 STL C++ 中搜索](https://www.geeksforgeeks.org/searching-map-using-stdmap-functions-c/)

本文由 [**【曼吉特·辛格】**](https://www.facebook.com/manjeet.04.singh) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。