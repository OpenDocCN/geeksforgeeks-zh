# c++ 标准模板库(STL)中的多集

> 原文:[https://www.geeksforgeeks.org/multiset-in-cpp-stl/](https://www.geeksforgeeks.org/multiset-in-cpp-stl/)

多集是一种类似于集合的关联容器，不同的是多个元素可以有相同的值。
与多集相关联的一些基本函数:
[begin()](https://www.geeksforgeeks.org/multiset-begin-and-end-function-in-c-stl/)–返回多集中第一个元素的迭代器
[end()](https://www.geeksforgeeks.org/multiset-begin-and-end-function-in-c-stl/)–返回多集中最后一个元素后面的理论元素的迭代器
[size()](https://www.geeksforgeeks.org/multiset-size-in-c-stl-with-examples/)–返回多集中元素的个数
[max _ size()](https://www.geeksforgeeks.org/multiset-max_size-in-c-stl/)–返回多集可以容纳的最大元素个数
[empty()](https://www.geeksforgeeks.org/multiset-empty-function-in-c-stl/)–返回

实施:

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
#include <set>
#include <iterator>

using namespace std;

int main()
{
    // empty multiset container
    multiset <int, greater <int> > gquiz1;       

    // insert elements in random order
    gquiz1.insert(40);
    gquiz1.insert(30);
    gquiz1.insert(60);
    gquiz1.insert(20);
    gquiz1.insert(50);

    // 50 will be added again to
    // the multiset unlike set
    gquiz1.insert(50);
    gquiz1.insert(10);

    // printing multiset gquiz1
    multiset <int, greater <int> > :: iterator itr;
    cout << "\nThe multiset gquiz1 is : \n";
    for (itr = gquiz1.begin(); itr
         != gquiz1.end(); ++ itr)
    {
        cout << *itr << " ";
    }
    cout << endl;

    // assigning the elements from gquiz1 to gquiz2
    multiset <int> gquiz2(gquiz1.begin()
                          , gquiz1.end());

    // print all elements of the multiset gquiz2
    cout << "\nThe multiset gquiz2 \n"
             "after assign from gquiz1 is : \n";
    for (itr = gquiz2.begin(); itr
         != gquiz2.end(); ++ itr)
    {
        cout << *itr <<" ";
    }
    cout << endl;

    // remove all elements up to element
   // with value 30 in gquiz2
    cout << "\ngquiz2 after removal \n"
            "of elements less than 30 : \n";
    gquiz2.erase(gquiz2.begin()
                 , gquiz2.find(30));
    for (itr = gquiz2.begin(); itr
         != gquiz2.end(); ++ itr)
    {
        cout << *itr << " " ;
    }

    // remove all elements with value 50 in gquiz2
    int num;
    num = gquiz2.erase(50);
    cout << "\ngquiz2.erase(50) : \n";
    cout << num << " removed \n" ;
    for (itr = gquiz2.begin(); itr
         != gquiz2.end(); ++ itr)
    {
        cout  << *itr << " ";
    }

    cout << endl;

    //lower bound and upper bound for multiset gquiz1
    cout << "\ngquiz1.lower_bound(40) : \n"
         << *gquiz1.lower_bound(40) << endl;
    cout << "gquiz1.upper_bound(40) : \n"
         << *gquiz1.upper_bound(40) << endl;

    //lower bound and upper bound for multiset gquiz2
    cout << "gquiz2.lower_bound(40) : \n"
         << *gquiz2.lower_bound(40) << endl;
    cout << "gquiz2.upper_bound(40) : \n"
         << *gquiz2.upper_bound(40) << endl;

         return 0;

}
```

**Output**

```cpp
The multiset gquiz1 is : 
60 50 50 40 30 20 10 

The multiset gquiz2 
after assign from gquiz1 is : 
10 20 30 40 50 50 60 

gquiz2 after removal 
of elements less than 30 : 
30 40 50 50 60 
gquiz2.erase(50) : 
2 removed 
30 40 60 

gquiz1.lower_bound(40) : 
40
gquiz1.upper_bound(40) : 
30
gquiz2.lower_bound(40) : 
40
gquiz2.upper_bound(40) : 
60
```

**从具有相同值的多集合中移除元素**

*   a . erase()–从具有相同值的多集中移除元素的所有实例
*   a . erase(a . find())–从具有相同值的多集中仅删除一个元素实例

## C++

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    multiset<int> a;
    a.insert(10);
    a.insert(10);
    a.insert(10);

    // it will give output 3
    cout << a.count(10) << endl;

    // removing single instance from multiset

    // it will remove only one value of
    // 10 from multiset
    a.erase(a.find(10));

    // it will give output 2
    cout << a.count(10) << endl;

    // removing all instance of element from multiset
    // it will remove all instance of value 10
    a.erase(10);

    // it will give output 0 because all
    // instance of value is removed from
    // multiset
    cout << a.count(10)
         << endl;

    return 0;
}
```

**Output**

```cpp
3
2
0
```

**多集功能列表:**

*   [begin()](https://www.geeksforgeeks.org/multiset-begin-and-end-function-in-c-stl/)–返回多集合中第一个元素的迭代器。
*   [end()](https://www.geeksforgeeks.org/multiset-begin-and-end-function-in-c-stl/)–返回多集最后一个元素之后的理论元素的迭代器。
*   [size()](https://www.geeksforgeeks.org/multiset-size-in-c-stl-with-examples/)–返回多集合中的元素数量。
*   [max _ size()](https://www.geeksforgeeks.org/multiset-max_size-in-c-stl/)–返回多集可以容纳的最大元素数。
*   [空()](https://www.geeksforgeeks.org/multiset-empty-function-in-c-stl/)–返回多集是否为空。
*   [成对插入(const g)](https://www.geeksforgeeks.org/multiset-insert-function-in-c-stl/)–向多集添加新元素“g”。
*   [迭代器插入(迭代器位置，const g)](https://www.geeksforgeeks.org/multiset-insert-function-in-c-stl/)–在迭代器指向的位置添加新元素‘g’。
*   [删除(迭代器位置)](https://www.geeksforgeeks.org/multiset-erase-in-c-stl/)–删除迭代器指向位置的元素。
*   [擦除(常量 g)](https://www.geeksforgeeks.org/multiset-erase-in-c-stl/)–从多集删除值“g”。
*   [清除()](https://www.geeksforgeeks.org/multiset-clear-function-in-c-stl/)–从多集移除所有元素。
*   [key _ comp()](https://www.geeksforgeeks.org/multiset-key_comp-function-in-c-stl/)/[value _ comp()](https://www.geeksforgeeks.org/multiset-value_comp-method-in-c-stl/)–返回确定多集元素排序方式的对象(默认情况下为“<”)。
*   [find(const g)](https://www.geeksforgeeks.org/multiset-find-function-in-c-stl/)–如果找到，返回一个迭代器到多集的元素‘g’，否则返回迭代器结束。
*   [count(const g)](https://www.geeksforgeeks.org/multiset-count-function-in-c-stl/)–返回多集合中元素“g”的匹配数。
*   [下界(const g)](https://www.geeksforgeeks.org/multiset-lower_bound-in-cpp-stl-with-examples/)–返回第一个元素的迭代器，该迭代器相当于“g”，或者如果找到，肯定不会在多集的元素“g”之前，否则返回迭代器结束。
*   [upper _ bound(const g)](https://www.geeksforgeeks.org/multiset-upper_bound-in-cpp-stl-with-examples/)–返回第一个元素的迭代器，该迭代器相当于“g”，或者如果找到，肯定会在多集中的元素“g”之后，否则返回迭代器结束。
*   [多集::swap()](https://www.geeksforgeeks.org/multisetswap-c-stl/)–此功能用于交换两个多集的内容，但集必须是相同类型，尽管大小可能不同。
*   [多集::运算符=](https://www.geeksforgeeks.org/multisetoperator-c-stl/)–该运算符用于通过替换现有内容向容器分配新内容。
*   [多集::侵位()](https://www.geeksforgeeks.org/multisetemplace-c-stl/)–此功能用于向多集容器中插入新元素。
*   [多集 equal _ range()](https://www.geeksforgeeks.org/multiset-equal_range-function-in-c-stl/)–返回一个对的迭代器。该对指的是包含容器中所有元素的范围，这些元素的键等价于 k。
*   [多集::侵位 _ 提示()](https://www.geeksforgeeks.org/multiset-emplace_hint-function-in-c-stl/)–在多集中插入新元素。
*   [多集::rbe gin()](https://www.geeksforgeeks.org/multiset-rbegin-and-rend-function-in-c-stl/)–返回指向多集容器中最后一个元素的反向迭代器。
*   [多集::rend()](https://www.geeksforgeeks.org/multiset-rbegin-and-rend-function-in-c-stl/)–返回一个反向迭代器，指向多集容器中第一个元素之前的理论元素。
*   [multist::CBE gin()](https://www.geeksforgeeks.org/multiset-cbegin-and-cend-function-in-c-stl/)–返回指向容器中第一个元素的常量迭代器。
*   [multist::cend()](https://www.geeksforgeeks.org/multiset-cbegin-and-cend-function-in-c-stl/)–返回一个常量迭代器，指向容器中最后一个元素之后的位置。
*   [multist::Cr begin()](https://www.geeksforgeeks.org/multiset-crbegin-and-crend-function-in-c-stl/)–返回指向容器中最后一个元素的常量反向迭代器。
*   [multist::crend()](https://www.geeksforgeeks.org/multiset-crbegin-and-crend-function-in-c-stl/)–返回一个常量反向迭代器，指向容器中第一个元素之前的位置。
*   [多集::get _ 分配器()](https://www.geeksforgeeks.org/multiset-get_allocator-function-in-c-stl/)–返回与多集关联的分配器对象的副本。

[**多集上最近的文章**](https://www.geeksforgeeks.org/tag/cpp-multiset/)

？list = plqm7 alhxfysg6 gsrme 2 ini 4k 8 fph5 qvb
如果发现有不正确的地方请写评论，或者想分享更多关于上面讨论的话题的信息