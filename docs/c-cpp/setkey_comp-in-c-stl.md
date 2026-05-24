# 在 C++ STL 中设置::key_comp()

> 原文:[https://www.geeksforgeeks.org/setkey_comp-in-c-stl/](https://www.geeksforgeeks.org/setkey_comp-in-c-stl/)

**set::key_comp()** 是 C++ STL 中的一个内置函数，它返回容器使用的比较对象的副本。默认情况下，这是一个较少的对象，返回与运算符**相同的值。这个对象决定了容器中元素的顺序。它是一个函数指针或函数对象，采用两个相同类型的参数作为容器元素，如果第一个参数在它定义的严格弱排序中被认为在第二个参数之前，则返回 *true* ，否则返回 false。如果 key_comp 反射性地返回 *false* ，则集合中的两个元素被认为是等价的(即，无论元素作为参数传递的顺序如何)。**

****语法:****

 ```cpp
key_compare set_name.key_comp() 

```** 

**参数:**此功能不接受任何参数。

**返回值:**函数返回容器使用的比较对象的副本。

演示上述功能的程序:

```cpp
// C++ program to illustrate the
// set::key_comp() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // creating a set named 'a'
    set<int> a;

    set<int>::key_compare comp = a.key_comp();

    // Inserting elements into set
    for (int i = 0; i <= 10; i++)
        a.insert(i);

    cout << "Set a has the numbers: ";

    // stores the last value of the set
    int l = *a.rbegin();

    // initialising the iterator
    set<int>::iterator it = a.begin();

    // printing elements of all set
    do {
        cout << *it << " ";
    } while (comp(*(++ it), l));

    return 0;
}
```

**Output:**

```cpp
Set a has the numbers: 0 1 2 3 4 5 6 7 8 9

```

'<>