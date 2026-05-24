# c++ STL 中的 forward_list insert_after()函数

> 原文:[https://www . geesforgeks . org/forward _ list-insert _ after-function-in-c-STL/](https://www.geeksforgeeks.org/forward_list-insert_after-function-in-c-stl/)

**forward_list::insert _ after()**是 C++ STL 中的一个内置函数，它让我们可以选择在 forward _ list 中给定迭代器所指向的元素之后的位置插入元素。此函数中的参数被复制到所需的位置。

**语法:**

```cpp
***forward_list_name.insert_after(iterator position, element)***

or,

***forward_list_name.insert_after(iterator position, n, element)***

or,

***forward_list_name.insert_after(iterator position, itr1, itr2)***

or,

*forward_list_name.insert_after(iterator position, list)*

```

**参数:**函数根据以上不同的语法接受不同的参数。让我们详细看看每个参数以及上面语法的工作原理。

*   **位置，元素:**参数*位置*属于迭代器类型，它指向参数*元素*的值要插入的位置。
*   **位置，n，元素:**参数*位置*属于迭代器类型，它指向参数*元素*的值要插入的位置。参数 *n* 指定插入值元素的次数。
*   **位置，itr1，itr2:** 参数*位置*属于迭代器类型，它指向要插入值的位置。迭代器 itr1 和 itr2 表示一个范围[itr1，itr2]，该范围内包括 itr1 和不包括 itr2 的元素将被插入到迭代器指向给定的*位置*之后的前向列表中。
*   **位置，列表:**参数*位置*属于迭代器类型，它指向值要插入的位置。第二个参数*列表*定义了要插入 forward_list 的元素列表。

**返回值:**这个函数返回一个迭代器，指向最后插入的元素。

下面的程序说明了上述功能:

```cpp
// C++ program to illustrate the
// forward_list::insert_after() function
#include <forward_list>
#include <iostream>
#include <list>

using namespace std;

int main()
{

    forward_list<int> fwlist = { 1, 2, 3, 4, 5 };
    list<int> sampleList = { 8, 9, 10 };

    // This iterator points to the first element
    auto it_new = fwlist.begin();

    // New element to be inserted
    int element = 20;

    /******************************/
    /** IMPLEMENTING SYNTAX 1 *****/
    /******************************/
    it_new = fwlist.insert_after(it_new, element);

    cout << "After Syntax 1: ";
    for (auto it = fwlist.cbegin(); it != fwlist.cend(); it++) {
        cout << *it << " ";
    }

    // it_new points to new element inserted which is 20
    // Make it to point to next element
    it_new++ ;

    /******************************/
    /** IMPLEMENTING SYNTAX 2 *****/
    /******************************/
    it_new = fwlist.insert_after(it_new, 3, element);

    cout << "\n\nAfter Syntax 2: ";
    for (auto it = fwlist.cbegin(); it != fwlist.cend(); it++) {
        cout << *it << " ";
    }

    /******************************/
    /** IMPLEMENTING SYNTAX 3 *****/
    /******************************/
    it_new = fwlist.insert_after(it_new, sampleList.begin(),
                                 sampleList.end());

    cout << "\n\nAfter Syntax 3: ";
    for (auto it = fwlist.cbegin(); it != fwlist.cend(); it++) {
        cout << *it << " ";
    }

    /******************************/
    /** IMPLEMENTING SYNTAX 4 *****/
    /******************************/
    it_new = fwlist.insert_after(it_new, { 50, 60 });

    cout << "\n\nAfter Syntax 4: ";
    for (auto it = fwlist.cbegin(); it != fwlist.cend(); it++) {
        cout << *it << " ";
    }

    return 0;
}
```

**Output:**

```cpp
After Syntax 1: 1 20 2 3 4 5 

After Syntax 2: 1 20 2 20 20 20 3 4 5 

After Syntax 3: 1 20 2 20 20 20 8 9 10 3 4 5 

After Syntax 4: 1 20 2 20 20 20 8 9 10 50 60 3 4 5

```