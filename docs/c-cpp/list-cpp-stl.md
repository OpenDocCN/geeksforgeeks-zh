# c++ 标准模板库(STL)中的列表

> 原文:[https://www.geeksforgeeks.org/list-cpp-stl/](https://www.geeksforgeeks.org/list-cpp-stl/)

列表是允许非连续内存分配的序列容器。与向量相比，列表遍历速度慢，但是一旦找到位置，插入和删除就很快。通常，当我们说一个列表时，我们说的是双链表。为了实现单链表，我们使用正向链表。

下面是展示 List 部分功能工作的程序:

```cpp
#include <iostream>
#include <list>
#include <iterator>
using namespace std;

//function for printing the elements in a list
void showlist(list <int> g)
{
    list <int> :: iterator it;
    for(it = g.begin(); it != g.end(); ++ it)
        cout << '\t' << *it;
    cout << '\n';
}

int main()
{

    list <int> gqlist1, gqlist2;

    for (int i = 0; i < 10; ++ i)
    {
        gqlist1.push_back(i * 2);
        gqlist2.push_front(i * 3);
    }
    cout << "\nList 1 (gqlist1) is : ";
    showlist(gqlist1);

    cout << "\nList 2 (gqlist2) is : ";
    showlist(gqlist2);

    cout << "\ngqlist1.front() : " << gqlist1.front();
    cout << "\ngqlist1.back() : " << gqlist1.back();

    cout << "\ngqlist1.pop_front() : ";
    gqlist1.pop_front();
    showlist(gqlist1);

    cout << "\ngqlist2.pop_back() : ";
    gqlist2.pop_back();
    showlist(gqlist2);

    cout << "\ngqlist1.reverse() : ";
    gqlist1.reverse();
    showlist(gqlist1);

    cout << "\ngqlist2.sort(): ";
    gqlist2.sort();
    showlist(gqlist2);

    return 0;

}
```

上述程序的输出是:

```cpp
List 1 (gqlist1) is :     0    2    4    6    
8    10    12    14    16    18

List 2 (gqlist2) is :     27    24    21    18    
15    12    9    6    3    0

gqlist1.front() : 0
gqlist1.back() : 18
gqlist1.pop_front() :     2    4    6    8    
10    12    14    16    18

gqlist2.pop_back() :     27    24    21    18    
15    12    9    6    3

gqlist1.reverse() :     18    16    14    12    
10    8    6    4    2

gqlist2.sort():     3    6    9    12    
15    18    21    24    27

```

**与 List 一起使用的函数:**

*   [[front ()]](https://www.geeksforgeeks.org/list-front-function-in-c-stl/) -Returns the value of the first element in the list.
*   [back ()](https://www.geeksforgeeks.org/list-back-function-in-c-stl/) -Returns the value of the last element in the list.
*   [Push _ front (g)](https://www.geeksforgeeks.org/list-push_front-function-in-c-stl/) -Add a new element' g' at the beginning of the list.
*   [Push _ back (g)](https://www.geeksforgeeks.org/list-push_back-function-in-c-stl/) -Add a new element' g' at the end of the list.
*   [pop _ front ()](https://www.geeksforgeeks.org/list-pop_front-function-in-c-stl/) –Remove the first element of the list and reduce the size of the list by 1.
*   [pop _ back ()](https://www.geeksforgeeks.org/list-pop_back-function-in-c-stl/) –Remove the last element of the list and reduce the size of the list by 1.
*   [list:: begin () and list::end () In C++ STL](https://www.geeksforgeeks.org/listbegin-listend-c-stl/) – **begin ()** function returns an iterator that points to the first element of the list.
*   [end ()](https://www.geeksforgeeks.org/list-end-function-in-c-stl/) – **end ()** function returns an iterator that points to the last element in theory.
*   [List rbegin () and rend () functions in C++ STL](https://www.geeksforgeeks.org/list-rbegin-and-rend-function-in-c-stl/) – **rbegin ()** Returns an inverse iterator pointing to the last element in the list. **Rend ()** Returns an inverse iterator, which points to the position before the start of the list.
*   [List the functions of cbegin () and cend () in C++ STL](https://www.geeksforgeeks.org/list-cbegin-and-cend-function-in-c-stl/) – **CBEGIN ()** Return a constant random access iterator pointing to the beginning of the list. **CEND ()** Returns a constant random access iterator pointing to the end of the list.
*   [The list crbegin () and crend () functions in C++ STL](https://www.geeksforgeeks.org/list-crbegin-and-crend-function-in-c-stl/) – **crbegin ()** return a constant inverse iterator that points to the last element of the list, that is, the inverse beginning of the container. **Crend ()** Returns a constant inverse iterator, which points to the theoretical element before the first element in the list, that is, the inverse end of the list.
*   [Empty ()](https://www.geeksforgeeks.org/list-empty-function-in-c-stl/) -Returns whether the list is empty (1) or not (0).
*   [Insert ()](https://www.geeksforgeeks.org/list-insert-in-c-stl/) –Insert a new element before the element at the specified position in the list.
*   [erase ()](https://www.geeksforgeeks.org/list-erase-function-in-c-stl/) –Remove a single element or a series of elements from the list.
*   [Assign ()](https://www.geeksforgeeks.org/list-assign-function-in-c-stl/) –Assign a new element to the list by replacing the current element and resize the list.
*   [Remove ()](https://www.geeksforgeeks.org/list-remove-function-in-c-stl/) –Delete all elements equal to the given element from the list.
*   [List:: Remove _ if ()](https://www.geeksforgeeks.org/listremove-listremove_if-c-stl/) in C++ STL-used to delete all true values corresponding to predicates or conditions given as function parameters from the list.
*   [Invert ()](https://www.geeksforgeeks.org/list-reverse-function-in-c-stl/) -Invert the list.
*   [size ()](https://www.geeksforgeeks.org/list-size-function-in-c-stl/) -Returns the number of elements in the list.
*   [list resize () function](https://www.geeksforgeeks.org/list-resize-function-in-c-stl/) in C++ STL-used to resize the list container.
*   [sort ()](https://www.geeksforgeeks.org/stdlistsort-c-stl/) –Sort the list in ascending order.
*   [The list max_size () function in C++ STL](https://www.geeksforgeeks.org/list-max_size-function-in-c-stl/) -returns the maximum prime number that the list container can hold.
*   [List unique ()](https://www.geeksforgeeks.org/list-unique-in-c-stl/) in C++ STL-Remove all duplicate continuous elements from the list.
*   [list:: Infringement _front () and List:: Infringement _back () In C++ STL](https://www.geeksforgeeks.org/listemplace_front-listemplace_back-c-stl/) – **Infringement _ front ()** function is used to insert new elements into the list container, and the new elements are added to the beginning of the list. **Insert _ back ()** The function is used to insert new elements into the list container, and the new elements are added to the end of the list.
*   [list:: clear () In C++ STL, the](https://www.geeksforgeeks.org/listclear-c-stl/) – **clear ()** function is used to remove all elements of the list container so that its size is 0.
*   [list:: operator =](https://www.geeksforgeeks.org/listoperator-c-stl/) in C++ STL-This operator is used to assign new content to the container by replacing existing content.
*   [List: swap () in C++ STL](https://www.geeksforgeeks.org/listswap-c-stl/) –This function is used to exchange the contents of one list with another list of the same type and size.
*   [List splicing () function in C++ STL](https://www.geeksforgeeks.org/list-splice-function-in-c-stl/) –used to transfer elements from one list to another.
*   [List merging () function in C++ STL](https://www.geeksforgeeks.org/list-merge-function-in-c-stl/) -Merge two sorted lists into one.
*   [List Bite () function in C++ STL](https://www.geeksforgeeks.org/list-emplace-function-in-c-stl/) -Expand the list by inserting new elements in a given position.

**[最近 C++ 上的文章列表](https://www.geeksforgeeks.org/tag/cpp-list/)**

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论