# c++ 中的转发列表|集 1(简介和重要功能)

> 原文:[https://www . geesforgeks . org/forward-list-c-set-1-introduction-important-functions/](https://www.geeksforgeeks.org/forward-list-c-set-1-introduction-important-functions/)

STL 中的正向列表实现了单链表。从 C++ 11 引入的正向列表在插入、移除和移动操作(如排序)方面比其他容器更有用，并且允许元素的时间常数插入和移除。
它与[列表](https://www.geeksforgeeks.org/list-cpp-stl/)的不同之处在于正向列表只跟踪下一个元素的位置，而列表同时跟踪下一个和上一个元素，因此增加了存储每个元素所需的存储空间。正向列表的缺点是不能反向迭代，不能直接访问单个元素。
当只需要正向遍历时，正向列表优于列表(与单链表优于双链表相同)，这样可以节省空间。一些例子是，散列中的链接，图的邻接表表示等。
**远期清单操作:**
**1。**[**assign()**](https://www.geeksforgeeks.org/forward_list-assign-function-in-c-stl/)**:-这个函数用来给转发列表赋值，它的另一个变体用来赋值重复的元素。** 

## **卡片打印处理机（Card Print Processor 的缩写）**

```cpp
// C++ code to demonstrate forward list
// and assign()
#include<iostream>
#include<forward_list>
using namespace std;

int main()
{
    // Declaring forward list
    forward_list<int> flist1;

    // Declaring another forward list
    forward_list<int> flist2;

    // Assigning values using assign()
    flist1.assign({1, 2, 3});

    // Assigning repeating values using assign()
    // 5 elements with value 10
    flist2.assign(5, 10);

    // Displaying forward lists
    cout << "The elements of first forward list are : ";
    for (int&a : flist1)
        cout << a << " ";
    cout << endl;

    cout << "The elements of second forward list are : ";
    for (int&b : flist2)
        cout << b << " ";
    cout << endl;

    return 0;
}
```

**输出:** 

```cpp
The elements of first forward list are : 1 2 3 
The elements of second forward list are : 10 10 10 10 10
```

 ****2。**[**push _ front()**](https://www.geeksforgeeks.org/forward_listpush_front-forward_listpop_front-c-stl/):-此功能用于将元素插入前进列表的第一个位置。该函数的值被复制到容器中第一个元素之前的空间。转发列表的大小增加 1。
**3。** [**侵位 _front()**](https://www.geeksforgeeks.org/forward_listemplace_front-in-cstl/) :-该函数与前一个函数类似，但在这种情况下不会发生复制操作，元素直接在内存中创建在前向列表的第一个元素之前。
**4。**[**pop _ front()**](https://www.geeksforgeeks.org/forward_listpush_front-forward_listpop_front-c-stl/):-此功能用于删除列表的第一个元素。** 

## **卡片打印处理机（Card Print Processor 的缩写）**

```cpp
// C++ code to demonstrate working of
// push_front(), emplace_front() and pop_front()
#include<iostream>
#include<forward_list>
using namespace std;

int main()
{
    // Initializing forward list
    forward_list<int> flist = {10, 20, 30, 40, 50};

    // Inserting value using push_front()
    // Inserts 60 at front
    flist.push_front(60);

    // Displaying the forward list
    cout << "The forward list after push_front operation : ";
    for (int&c : flist)
        cout << c << " ";
    cout << endl;

    // Inserting value using emplace_front()
    // Inserts 70 at front
    flist.emplace_front(70);

    // Displaying the forward list
    cout << "The forward list after emplace_front operation : ";
    for (int&c : flist)
       cout << c << " ";
    cout << endl;

    // Deleting first value using pop_front()
    // Pops 70
    flist.pop_front();

    // Displaying the forward list
    cout << "The forward list after pop_front operation : ";
    for (int&c : flist)
        cout << c << " ";
    cout << endl;

    return 0;
}
```

**输出:** 

```cpp
The forward list after push_front operation : 60 10 20 30 40 50 
The forward list after emplace_front operation : 70 60 10 20 30 40 50 
The forward list after pop_front operation : 60 10 20 30 40 50
```

****4。**[**insert _ after()**](https://www.geeksforgeeks.org/forward_list-insert_after-function-in-c-stl/)这个功能给了我们一个选择，可以在前向列表的任意位置插入元素。此函数中的参数被复制到所需的位置。
**5。** [**侵位 _after()**](https://www.geeksforgeeks.org/forward_list-emplace_after-and-emplace_front-in-c-stl/) 这个功能也做了和上面功能一样的操作，但是元素是直接制作的，没有任何复制操作。
**6。**[**erase _ after()**](https://www.geeksforgeeks.org/forward_listclear-forward_listerase_after-c-stl/)**此功能用于从正向列表中的特定位置擦除元素。**** 

## ****卡片打印处理机（Card Print Processor 的缩写）****

```cpp
**// C++ code to demonstrate working of
// insert_after(), emplace_after() and erase_after()
#include<iostream>
#include<forward_list>
using namespace std;

int main()
{
    // Initializing forward list
    forward_list<int> flist = {10, 20, 30} ;

    // Declaring a forward list iterator
    forward_list<int>::iterator ptr;

    // Inserting value using insert_after()
    // starts insertion from second position
    ptr =  flist.insert_after(flist.begin(), {1, 2, 3});

    // Displaying the forward list
    cout << "The forward list after insert_after operation : ";
    for (int&c : flist)
        cout << c << " ";
    cout << endl;

    // Inserting value using emplace_after()
    // inserts 2 after ptr
    ptr = flist.emplace_after(ptr,2);

    // Displaying the forward list
    cout << "The forward list after emplace_after operation : ";
    for (int&c : flist)
        cout << c << " ";
    cout << endl;

    // Deleting value using erase.after Deleted 2
    // after ptr
    ptr = flist.erase_after(ptr);

    // Displaying the forward list
    cout << "The forward list after erase_after operation : ";
    for (int&c : flist)
        cout << c << " ";
    cout << endl;

    return 0;
}**
```

****输出:**** 

```cpp
**The forward list after insert_after operation : 10 1 2 3 20 30 
The forward list after emplace_after operation : 10 1 2 3 2 20 30 
The forward list after erase_after operation : 10 1 2 3 2 30**
```

******7。** [**remove()**](https://www.geeksforgeeks.org/forward_listremove-forward_listremove_if-c-stl/) :-该函数从其参数中提到的转发列表中删除特定元素。
**8。**[**remove _ if()**](https://www.geeksforgeeks.org/forward_listremove-forward_listremove_if-c-stl/):-该函数根据其参数中的条件进行删除。**** 

## ****卡片打印处理机（Card Print Processor 的缩写）****

```cpp
**// C++ code to demonstrate working of remove() and
// remove_if()
#include<iostream>
#include<forward_list>
using namespace std;

int main()
{
    // Initializing forward list
    forward_list<int> flist = {10, 20, 30, 25, 40, 40};

    // Removing element using remove()
    // Removes all occurrences of 40
    flist.remove(40);

    // Displaying the forward list
    cout << "The forward list after remove operation : ";
    for (int&c : flist)
        cout << c << " ";
    cout << endl;

    // Removing according to condition. Removes
    // elements greater than 20\. Removes 25 and 30
    flist.remove_if([](int x){ return x>20;});

    // Displaying the forward list
    cout << "The forward list after remove_if operation : ";
    for (int&c : flist)
       cout << c << " ";
    cout << endl;

    return 0;

}**
```

****输出:**** 

```cpp
**The forward list after remove operation : 10 20 30 25 
The forward list after remove_if operation : 10 20**
```

******9。** [**【拼接 _after()**](https://www.geeksforgeeks.org/forward_listsplice_after-in-c-stl/) :-该功能将元素从一个转发列表转移到另一个转发列表。**** 

## ****卡片打印处理机（Card Print Processor 的缩写）****

```cpp
**// C++ code to demonstrate working of
// splice_after()
#include<iostream>
#include<forward_list> // for splice_after()
using namespace std;

int main()
{
    // Initializing forward list
    forward_list<int> flist1 = {10, 20, 30};

    // Initializing second list
    forward_list<int> flist2 = {40, 50, 60};

    // Shifting elements from first to second
    // forward list after 1st position
    flist2.splice_after(flist2.begin(),flist1);

    // Displaying the forward list
    cout << "The forward list after splice_after operation : ";
    for (int&c : flist2)
       cout << c << " ";
    cout << endl;

    return 0;
}**
```

****输出:**** 

```cpp
**The forward list after splice_after operation : 40 10 20 30 50 60**
```

******转发列表的更多方法:****** 

*   ****[front()](https://www.geeksforgeeks.org/forward_listfront-forward_listempty-c-stl/)–该函数用于引用正向列表容器的第一个元素。****
*   ****[begin()](https://www.geeksforgeeks.org/forward_listbegin-forward_listend-c-stl/)–begin()函数用于返回指向正向列表容器第一个元素的迭代器。****
*   ****[end()](https://www.geeksforgeeks.org/forward_listbegin-forward_listend-c-stl/)–end()函数用于返回指向列表容器最后一个元素的迭代器。****
*   ****[CBE gin()](https://www.geeksforgeeks.org/forward_list-cbegin-in-c-stl/)–返回指向 forward_list 第一个元素的常量迭代器。****
*   ****[cend()](https://www.geeksforgeeks.org/forward_listcend-in-c-stl-with-example/)–返回指向 forward_list 最后一个元素的常量迭代器。****
*   ****[before _ begin()](https://www.geeksforgeeks.org/forward_listbefore_begin-in-c-stl/)–返回一个迭代器，该迭代器指向 forward_list 第一个元素之前的位置。****
*   ****[CBE fore _ begin()](https://www.geeksforgeeks.org/forward_listcbefore_begin-in-c-stl/)–返回一个常量随机访问迭代器，该迭代器指向 forward_list 第一个元素之前的位置。****
*   ****[max _ size()](https://www.geeksforgeeks.org/forward_listmax_size-in-c-stl/)–返回 forward_list 可容纳的最大元素数。****
*   ****[调整大小()](https://www.geeksforgeeks.org/forward_list-resize-function-in-c-stl/)–更改 forward_list 的大小。****

****[c++ 中的转发列表|第二集(操纵函数)](https://www.geeksforgeeks.org/forward-list-c-set-2-manipulating-functions/)
本文由**曼吉特·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。****