# c++ 标准模板库(STL)中的多映射

> 原文:[https://www . geesforgeks . org/multimap-associative-containers-the-c-standard-template-library-STL/](https://www.geeksforgeeks.org/multimap-associative-containers-the-c-standard-template-library-stl/)

多重映射类似于[映射](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)，只是增加了多个元素可以有相同的键。此外，在这种情况下，不要求键值和映射值对必须是唯一的。关于 multimap 需要注意的一点是，multimap 始终保持所有键的排序顺序。multimap 的这些特性使得它在竞争性编程中非常有用。
**与多地图相关的一些基本功能:**

*   [**【begin()**](https://www.geeksforgeeks.org/multimapbegin-and-multimapend-in-c-stl/)–返回多映射中第一个元素的迭代器
*   [**【end()**](https://www.geeksforgeeks.org/multimapbegin-and-multimapend-in-c-stl/)–返回多映射中最后一个元素之后的理论元素的迭代器
*   [**【大小()**](https://www.geeksforgeeks.org/multimap-size-function-in-c-stl/)–返回多重映射中的元素数量
*   [**【max _ size()**](https://www.geeksforgeeks.org/multimap-maxsize-in-c-stl/)–返回多映射可以容纳的最大元素数量
*   [**【空()**](https://www.geeksforgeeks.org/multimap-empty-function-in-c-stl/)–返回多重映射是否为空
*   [**对< int，int > insert(keyvalue，multimap value**)](https://www.geeksforgeeks.org/multimap-insert-in-c-stl/)–向 multimap 添加新元素

**C++ 实现说明以上功能**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
#include <map>
#include <iterator>

using namespace std;

int main()
{
    multimap <int, int> gquiz1; // empty multimap container

    // insert elements in random order
    gquiz1.insert(pair <int, int> (1, 40));
    gquiz1.insert(pair <int, int> (2, 30));
    gquiz1.insert(pair <int, int> (3, 60));
    gquiz1.insert(pair <int, int> (6, 50));
    gquiz1.insert(pair <int, int> (6, 10));

    // printing multimap gquiz1
    multimap <int, int> :: iterator itr;
    cout << "\nThe multimap gquiz1 is : \n";
    cout << "\tKEY\tELEMENT\n";
    for (itr = gquiz1.begin(); itr != gquiz1.end(); ++ itr)
    {
        cout << '\t' << itr->first
            << '\t' << itr->second << '\n';
    }
    cout << endl;

    //adding elements randomly,
    // to check the sorted keys property
    gquiz1.insert(pair <int, int> (4, 50));
    gquiz1.insert(pair <int, int> (5, 10));

    // printing multimap gquiz1 again

    cout << "\nThe multimap gquiz1 after adding extra elements is : \n";
    cout << "\tKEY\tELEMENT\n";
    for (itr = gquiz1.begin(); itr != gquiz1.end(); ++ itr)
    {
        cout << '\t' << itr->first
            << '\t' << itr->second << '\n';
    }
    cout << endl;

    // assigning the elements from gquiz1 to gquiz2
    multimap <int, int> gquiz2(gquiz1.begin(),
                                gquiz1.end());

    // print all elements of the multimap gquiz2
    cout << "\nThe multimap gquiz2 after assign from gquiz1 is : \n";
    cout << "\tKEY\tELEMENT\n";
    for (itr = gquiz2.begin(); itr != gquiz2.end(); ++ itr)
    {
        cout << '\t' << itr->first
            << '\t' << itr->second << '\n';
    }
    cout << endl;

    // remove all elements up to
    // key with value 3 in gquiz2
    cout << "\ngquiz2 after removal of elements less than key=3 : \n";
    cout << "\tKEY\tELEMENT\n";
    gquiz2.erase(gquiz2.begin(), gquiz2.find(3));
    for (itr = gquiz2.begin(); itr != gquiz2.end(); ++ itr)
    {
        cout << '\t' << itr->first
            << '\t' << itr->second << '\n';
    }

    // remove all elements with key = 4
    int num;
    num = gquiz2.erase(4);
    cout << "\ngquiz2.erase(4) : ";
    cout << num << " removed \n" ;
    cout << "\tKEY\tELEMENT\n";
    for (itr = gquiz2.begin(); itr != gquiz2.end(); ++ itr)
    {
        cout << '\t' << itr->first
            << '\t' << itr->second << '\n';
    }

    cout << endl;

    //lower bound and upper bound for multimap gquiz1 key = 5
    cout << "gquiz1.lower_bound(5) : " << "\tKEY = ";
    cout << gquiz1.lower_bound(5)->first << '\t';
    cout << "\tELEMENT = " << gquiz1.lower_bound(5)->second << endl;
    cout << "gquiz1.upper_bound(5) : " << "\tKEY = ";
    cout << gquiz1.upper_bound(5)->first << '\t';
    cout << "\tELEMENT = " << gquiz1.upper_bound(5)->second << endl;

    return 0;
}
```

**Output**

```cpp
The multimap gquiz1 is : 
    KEY    ELEMENT
    1    40
    2    30
    3    60
    6    50
    6    10

The multimap gquiz1 after adding extra elements is : 
    KEY    ELEMENT
    1    40
    2    30
    3    60
    4    50
    5    10
    6    50
    6    10

The multimap gquiz2 after assign from gquiz1 is : 
    KEY    ELEMENT
    1    40
    2    30
    3    60
    4    50
    5    10
    6    50
    6    10

gquiz2 after removal of elements less than key=3 : 
    KEY    ELEMENT
    3    60
    4    50
    5    10
    6    50
    6    10

gquiz2.erase(4) : 1 removed 
    KEY    ELEMENT
    3    60
    5    10
    6    50
    6    10

gquiz1.lower_bound(5) :     KEY = 5        ELEMENT = 10
gquiz1.upper_bound(5) :     KEY = 6        ELEMENT = 50
```

**多地图功能列表:**

*   [multimap::operator=在 C++ STL 中](https://www.geeksforgeeks.org/multimapoperator-c-stl/)–用于通过替换现有内容为容器分配新内容。
*   [c++ STL](https://www.geeksforgeeks.org/multimapcrbegin-and-multimapcrend-in-c-stl/)–**crbegin()**中的 multimap::crbegin()和 multimap::crend()返回一个引用 multimap 容器中最后一个元素的常量反向迭代器。 **crend()** 返回一个常量反向迭代器，指向 multimap 中第一个元素之前的理论元素。
*   [c++ STL 中的多映射::侵位 _ 提示()](https://www.geeksforgeeks.org/multimapemplace_hint-in-c-stl/)–用给定的提示在多映射容器中插入键及其元素。
*   [c++ STL 中的 multimap clear()函数](https://www.geeksforgeeks.org/multimap-clear-function-in-c-stl/)–从 multimap 中移除所有元素。
*   [c++ STL 中的 multimap empty()函数](https://www.geeksforgeeks.org/multimap-empty-function-in-c-stl/)–返回 multimap 是否为空。
*   [c++ STL 中的 multimap maxsize()](https://www.geeksforgeeks.org/multimap-maxsize-in-c-stl/)–返回 multimap 容器可以容纳的最大元素数。
*   [c++ STL 中的 multimap value_comp()函数](https://www.geeksforgeeks.org/multimap-value_comp-function-in-c-stl/)–返回确定 multimap 中元素排序方式的对象(默认为“<”)
*   [c++ STL 中的多映射渲染](https://www.geeksforgeeks.org/multimap-rend-in-c-stl/)–返回一个反向迭代器，指向多映射容器第一个元素之前的理论元素。
*   [c++ STL](https://www.geeksforgeeks.org/multimapcbegin-and-multimapcend-in-c-stl/)–**CBE gin()**中的 multimap::cbegin()和 multimap::cend()返回引用 multimap 容器中第一个元素的常量迭代器。 **cend()** 返回一个常量迭代器，指向 multimap 中最后一个元素之后的理论元素。
*   [c++ STL 中的 multimap::Swap()](https://www.geeksforgeeks.org/multimapswap-c-stl/)–将一个 multimap 的内容与另一个相同类型和大小的 multi map 进行交换。
*   [c++ STL 中的多映射 rbegin](https://www.geeksforgeeks.org/multimap-rbegin-in-c-stl/)–返回指向容器最后一个元素的迭代器。
*   [c++ STL 中的 multimap size()函数](https://www.geeksforgeeks.org/multimap-size-function-in-c-stl/)–返回 multimap 容器中的元素个数。
*   [多映射::在 C++ STL 中放置()](https://www.geeksforgeeks.org/multimapemplace-in-c-stl/)–在多映射容器中插入键及其元素。
*   [c++ STL 中的 multimap::begin()和 multimap::end()](https://www.geeksforgeeks.org/multimapbegin-and-multimapend-in-c-stl/)–**begin()**返回引用 multimap 容器中第一个元素的迭代器。 **end()** 返回一个迭代器到 multimap 中最后一个元素之后的理论元素。
*   [c++ STL 中的 multimap upper _ bound()函数](https://www.geeksforgeeks.org/multimap-upper_bound-function-in-c-stl/)–返回第一个元素的迭代器，该元素相当于带有键值“g”的 multimap 值，或者肯定会在 multimap 中带有键值“g”的元素之后。
*   [c++ STL 中的 multimap::count()](https://www.geeksforgeeks.org/multimapcount-in-c-stl/)–返回与 multimap 中键值为“g”的元素匹配的次数。
*   [多映射::C++ STL 中的 erase()](https://www.geeksforgeeks.org/multimaperase-in-c-stl/)–从多映射中移除键值。
*   [c++ STL 中的 multimap::find()](https://www.geeksforgeeks.org/multimapfind-in-c-stl/)–返回一个迭代器到 multimap 中键值为‘g’的元素，如果找到，否则返回迭代器结束。
*   [c++ STL 中的 multimap equal _ range()](https://www.geeksforgeeks.org/multimap-equal_range-in-c-stl/)–返回一个对的迭代器。该对指的是一个范围的边界，该范围包括容器中所有具有与 k 等价的键的元素。
*   [c++ STL 中的 multimap insert()](https://www.geeksforgeeks.org/multimap-insert-in-c-stl/)–用于在 multi map 容器中插入元素。
*   [c++ STL 中的 multimap _ 下界()函数](https://www.geeksforgeeks.org/multimap-lower_bound-function-in-c-stl/)–返回第一个元素的迭代器，该元素相当于带有键值“g”的 multimapped value，或者肯定不会在 multimap 中带有键值“g”的元素之前。
*   [c++ STL 中的 multimap key _ comp()](https://www.geeksforgeeks.org/multimap-key_comp-in-c-stl/)–返回确定 multi map 中元素排序方式的对象(默认为“<”)。

[**最近在 Multimap 上的文章**](https://www.geeksforgeeks.org/tag/cpp-multimap/)
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论