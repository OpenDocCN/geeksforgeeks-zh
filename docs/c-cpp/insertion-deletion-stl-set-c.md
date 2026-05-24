# STL 集合 C++ 中的插入和删除

> 原文:[https://www.geeksforgeeks.org/insertion-deletion-stl-set-c/](https://www.geeksforgeeks.org/insertion-deletion-stl-set-c/)

[Set](https://www.geeksforgeeks.org/set-associative-containers-the-c-standard-template-library-stl/) 是一个在 STL 中用 C++ 语言实现的容器，其概念类似于数学中如何定义 Set。将 set 与其他容器分开的事实是，它只包含**不同的元素**，并且元素可以按排序顺序遍历。在竞争编程和解决算法问题时，对集合有很强的控制力是很有用的。本文讨论了 STL 集中的插入和删除。

**Insertion**

**使用 insert()** : Insert 功能用于插入集合中的元素。插入后，元素重新排序，集合被排序。该功能有三种实现方式。

*   **插入(ele)** :此功能插入集合中的元素。只有当通过的元素**不是已经设置好的**时，插入才会发生。**它返回一个指针对。指向已经存在或新插入的元素的第一个元素。返回布尔状态“真”或“假”的第二个元素。**
*   **插入(提示，ele)** :在这个实现中，**提示指针**与要插入的元素一起发送。使用提示指针是为了**帮助 insert()知道实际的插入必须发生在哪里**。因此，尝试减少分配元素的时间。提示指针不会强制在特定位置插入。该功能**将指针返回到插入元素的位置**。
*   **插入(beg_ptr，end_ptr)** :这种类型的插入需要**将其他容器**的元件插入到套件中。如果重复的元素出现在源容器中，则不会插入它们。

```cpp
// C++ code to demonstrate the working of insert()
#include<iostream>
#include<set> // for set operations
using namespace std;

int main()
{
    // declaring set
    set<int> st;

    // declaring iterators
    set<int>::iterator it = st.begin();
    set<int>::iterator it1, it2;

    // declaring pair for return value of set containing
    // set iterator and bool
    pair< set<int>::iterator,bool> ptr;

    // using insert() to insert single element
    // inserting 20
    ptr = st.insert(20);

    // checking if the element was already present or newly inserted
    if (ptr.second)
        cout << "The element was newly inserted" ;
    else cout  << "The element was already present" ;

    // printing set elements after insertion
    cout << "\nThe set elements after 1st insertion are : ";
    for (it1 = st.begin(); it1!=st.end();  ++ it1)
        cout << *it1 << " ";

    // inserting set elements using hint
    st.insert(it, 24);

    // printing set elements after insertion
    cout << "\nThe set elements after 2nd insertion are : ";
    for (it1 = st.begin(); it1!=st.end();  ++ it1)
        cout << *it1 << " ";

    // inserting array elements in set
    // 24 is not inserted again
    int arr[3] = { 25, 24, 26 };
    st.insert(arr, arr+3);

    // printing set elements after insertion
    cout << "\nThe set elements after 3rd insertion are : ";
    for (it1 = st.begin(); it1!=st.end();  ++ it1)
        cout << *it1 << " ";

}
```

输出:

```cpp
The element was newly inserted
The set elements after 1st insertion are : 20 
The set elements after 2nd insertion are : 20 24 
The set elements after 3rd insertion are : 20 24 25 26 

```

**使用定位**:定位也用于将元素插入到集合中。该功能类似于上面讨论的“insert()”，唯一的区别是**元素的“就地”构造发生在元素插入**的位置，与拷贝或电影现有对象的 insert()相反。

*   **定位()**:使用原地构建策略插入元素。将集合的大小增加 1。返回指针对。**第一个元素是迭代器，指向插入元素的位置。2nd 返回一个布尔变量，表示已经存在或新创建的元素**。
*   **侵位 _ 提示()**:取一个**“提示 _ 迭代器”得到插入位置的提示**可能会减少插入插入元素所需的时间。这不会影响插入的位置。它发生在内部定义的地方。

```cpp
// C++ code to demonstrate the working of emplace()
// and emplace_hint()
#include<iostream>
#include<set> // for set operations
using namespace std;

int main()
{
    // declaring set
    set<int> st;

    // declaring iterators
    set<int>::iterator it = st.begin();
    set<int>::iterator it1, it2;

    // declaring pair for return value of set containing
    // set iterator and bool
    pair< set<int>::iterator,bool> ptr;

    // using emplace() to insert single element
    // inserting 24
    ptr = st.emplace(24);

    // checking if the element was already present or
    // newly inserted returns true. newly inserted
    if (ptr.second)
        cout << "The element was newly inserted" ;
    else cout  << "The element was already present" ;

    // printing set elements after insertion
    cout << "\nThe set elements after 1st insertion are : ";
    for (it1 = st.begin(); it1!=st.end();  ++ it1)
        cout << *it1 << " ";

    // using emplace() to insert single element
    // inserting 24 // not inserted this time
    ptr = st.emplace(24);

    // checking if the element was already present or
    // newly inserted returns false. already inserted
    if (ptr.second)
        cout << "\nThe element was newly inserted" ;
    else cout  << "\nThe element was already present" ;

    // printing set elements after insertion
    cout << "\nThe set elements after 2nd insertion are : ";
    for (it1 = st.begin(); it1!=st.end();  ++ it1)
        cout << *it1 << " ";

    // inserting set elements using hint
    st.emplace_hint(it,25);

    // printing set elements after insertion
    cout << "\nThe set elements after 3rd insertion are : ";
    for (it1 = st.begin(); it1!=st.end();  ++ it1)
        cout << *it1 << " ";
}
```

输出:

```cpp
The element was newly inserted
The set elements after 1st insertion are : 24 
The element was already present
The set elements after 2nd insertion are : 24 
The set elements after 3rd insertion are : 24 25 

```

**Deletion**

**使用 erase()** : erase()用于**擦除**参数中提到的集合中的元素，可以是它的位置、它的值，也可以是一个数字范围。

*   **擦除(num)** :擦除其参数中提到的**值**。删除后对集合重新排序。
*   **擦除(iter)** :擦除其参数中提到的迭代器所指向位置的值**。**
*   **擦除(strt_iter，end_iter)** :擦除从“strt_iter”到“end_iter”的**元素范围**。

```cpp
// C++ code to demonstrate the working of erase()
#include<iostream>
#include<set> // for set operations
using namespace std;

int main()
{
    // declaring set
    set<int> st;

    // declaring iterators
    set<int>::iterator it;
    set<int>::iterator it1;
    set<int>::iterator it2;

    // declaring pair for return value of set containing
    // set iterator and bool
    pair< set<int>::iterator,bool> ptr;

    // inserting values in set
    for (int i=1; i<10; i++)
        st.insert(i*5);

    // printing initial set elements
    cout << "The set elements after insertion are : ";
    for (it1 = st.begin(); it1!=st.end();  ++ it1)
        cout << *it1 << " ";

    it = st.begin();

    cout << endl;

    // erasing element using iterator
    // erases 2nd element i.e., 10
    ++ it;
    st.erase(it);

    // printing set elements after deletion
    cout << "The set elements after 1st deletion are : ";
    for (it1 = st.begin(); it1!=st.end();  ++ it1)
        cout << *it1 << " ";

    // erasing element using value
    st.erase(40);

    // printing set elements after deletion
    cout << "\nThe set elements after 2nd deletion are : ";
    for (it1 = st.begin(); it1!=st.end();  ++ it1)
        cout << *it1 << " ";

    ++ it;
    ++ it;
    ++ it;
    ++ it;

    // erasing element using range iterator
    // deletes 25 - last(45)
    st.erase(it, st.end());

    // printing set elements 3rd deletion
    cout << "\nThe set elements after 3rd deletion are : ";
    for (it1 = st.begin(); it1!=st.end();  ++ it1)
        cout << *it1 << " ";

    cout << endl;
}
```

输出:

```cpp
The set elements after insertion are : 5 10 15 20 25 30 35 40 45 
The set elements after 1st deletion are : 5 15 20 25 30 35 40 45 
The set elements after 2nd deletion are : 5 15 20 25 30 35 45 
The set elements after 3rd deletion are : 5 15 20 

```

本文由 **[【曼吉特·辛格】](https://www.facebook.com/manjeet.04.singh)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。