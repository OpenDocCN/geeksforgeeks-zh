# C++ 标准模板库(STL)中的映射

> 原文：[https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)

映射是以映射方式存储元素的关联容器。每个元素都有一个键值和一个映射值。没有两个映射值可以具有相同的键值。

## 与地图相关联的一些基本函数

*   [`begin()`](https://www.geeksforgeeks.org/mapbegin-end-c-stl/) – 返回地图中第一个元素的迭代器
*   [`end()`](https://www.geeksforgeeks.org/mapbegin-end-c-stl/) – 返回地图中最后一个元素后面的理论元素的迭代器
*   [`size()`](https://www.geeksforgeeks.org/mapsize-c-stl/) – 返回地图中元素的数量
*   [`max_size()`](https://www.geeksforgeeks.org/map-max_size-in-c-stl/) – 返回地图可以容纳的最大元素数量
*   [`empty()`](https://www.geeksforgeeks.org/mapempty-c-stl/) – 返回地图是否为空
*   [`insert(keyvalue, mapvalue)`](https://www.geeksforgeeks.org/map-insert-in-c-stl/) – 向地图添加新元素
*   [`erase(iterator position)`](https://www.geeksforgeeks.org/map-erase-function-in-c-stl/) – 删除迭代器所指向位置的元素
*   [`erase(const g)`](https://www.geeksforgeeks.org/map-erase-function-in-c-stl/) – 从地图中删除键值“g”
*   [`clear()`](https://www.geeksforgeeks.org/mapclear-c-stl/) – 从地图中删除所有元素

```cpp
#include <iostream>
#include <iterator>
#include <map>

using namespace std;

int main()
{

// empty map container
    map<int, int> gquiz1;

// insert elements in random order
    gquiz1.insert(pair<int, int>(1, 40));
    gquiz1.insert(pair<int, int>(2, 30));
    gquiz1.insert(pair<int, int>(3, 60));
    gquiz1.insert(pair<int, int>(4, 20));
    gquiz1.insert(pair<int, int>(5, 50));
    gquiz1.insert(pair<int, int>(6, 50));
    gquiz1.insert(pair<int, int>(7, 10));

// printing map gquiz1
    map<int, int>::iterator itr;
    cout << "\nThe map gquiz1 is : \n";
    cout << "\tKEY\tELEMENT\n";
    for (itr = gquiz1.begin(); itr != gquiz1.end(); ++ itr) {
        cout << '\t' << itr->first
             << '\t' << itr->second << '\n';
    }
    cout << endl;

// assigning the elements from gquiz1 to gquiz2
    map<int, int> gquiz2(gquiz1.begin(), gquiz1.end());

// print all elements of the map gquiz2
    cout << "\nThe map gquiz2 after"
         << " assign from gquiz1 is : \n";
    cout << "\tKEY\tELEMENT\n";
    for (itr = gquiz2.begin(); itr != gquiz2.end(); ++ itr) {
        cout << '\t' << itr->first
             << '\t' << itr->second << '\n';
    }
    cout << endl;

// remove all elements up to
    // element with key=3 in gquiz2
    cout << "\ngquiz2 after removal of"
            " elements less than key=3 : \n";
    cout << "\tKEY\tELEMENT\n";
    gquiz2.erase(gquiz2.begin(), gquiz2.find(3));
    for (itr = gquiz2.begin(); itr != gquiz2.end(); ++ itr) {
        cout << '\t' << itr->first
             << '\t' << itr->second << '\n';
    }

// remove all elements with key = 4
    int num;
    num = gquiz2.erase(4);
    cout << "\ngquiz2.erase(4) : ";
    cout << num << " removed \n";
    cout << "\tKEY\tELEMENT\n";
    for (itr = gquiz2.begin(); itr != gquiz2.end(); ++ itr) {
        cout << '\t' << itr->first
             << '\t' << itr->second << '\n';
    }

cout << endl;

// lower bound and upper bound for map gquiz1 key = 5
    cout << "gquiz1.lower_bound(5) : "
         << "\tKEY = ";
    cout << gquiz1.lower_bound(5)->first << '\t';
    cout << "\tELEMENT = "
         << gquiz1.lower_bound(5)->second << endl;
    cout << "gquiz1.upper_bound(5) : "
         << "\tKEY = ";
    cout << gquiz1.upper_bound(5)->first << '\t';
    cout << "\tELEMENT = "
         << gquiz1.upper_bound(5)->second << endl;

return 0;
}
```

## Output

```cpp
The map gquiz1 is : 
    KEY    ELEMENT
    1    40
    2    30
    3    60
    4    20
    5    50
    6    50
    7    10

The map gquiz2 after assign from gquiz1 is : 
    KEY    ELEMENT
    1    40
    2    30
    3    60
    4    20
    5    50
    6    50
    7    10

gquiz2 after removal of elements less than key=3 : 
    KEY    ELEMENT
    3    60
    4    20
    5    50
    6    50
    7    10

gquiz2.erase(4) : 1 removed 
    KEY    ELEMENT
    3    60
    5    50
    6    50
    7    10

gquiz1.lower_bound(5) :     KEY = 5        ELEMENT = 50
gquiz1.upper_bound(5) :     KEY = 6        ELEMENT = 50
```

## 地图所有功能列表

*   [`insert()`](https://www.geeksforgeeks.org/map-insert-in-c-stl/) – 在映射容器中插入带有特定键的元素。
*   [`count()`](https://www.geeksforgeeks.org/map-count-function-in-c-stl/) – 返回与映射中键值为‘g’的元素的匹配次数。
*   [`equal_range()`](https://www.geeksforgeeks.org/map-equal_range-in-c-stl/) – 返回一个对的迭代器。该对指的是一个范围的边界，该范围包括容器中所有具有与 k 等价的键的元素。
*   [`erase()`](https://www.geeksforgeeks.org/map-erase-function-in-c-stl/) – 用于从容器中擦除元素。
*   [`rend()`](https://www.geeksforgeeks.org/map-rend-function-in-c-stl/) – 返回一个反向迭代器，指向映射中第一个键值对之前的理论元素(被认为是其反向结束)。
*   [`rbegin()`](https://www.geeksforgeeks.org/map-rbegin-function-in-c-stl-2/) – 返回一个反向迭代器，它指向映射的最后一个元素。
*   [`find()`](https://www.geeksforgeeks.org/map-find-function-in-c-stl/) – 返回一个迭代器到映射中键值为‘g’的元素，如果找到，否则返回迭代器结束。
*   [`crbegin()`](https://www.geeksforgeeks.org/map-crbegin-and-crend-function-in-c-stl/) 和 [`crend()`](https://www.geeksforgeeks.org/map-crbegin-and-crend-function-in-c-stl/) – `crbegin()`返回一个引用映射容器中最后一个元素的常量反向迭代器。`crend()` 返回一个常量反向迭代器，指向映射中第一个元素之前的理论元素。
*   [`cbegin()`](https://www.geeksforgeeks.org/map-cbegin-and-cend-function-in-c-stl/) 和 [`cend()`](https://www.geeksforgeeks.org/map-cbegin-and-cend-function-in-c-stl/) – `cbegin()`返回引用映射容器中第一个元素的常量迭代器。`cend()` 返回一个常量迭代器，指向 multimap 中最后一个元素之后的理论元素。
*   [`emplace()`](https://www.geeksforgeeks.org/map-emplace-in-c-stl/) – 在地图容器中插入关键点及其元素。
*   [`max_size()`](https://www.geeksforgeeks.org/map-max_size-in-c-stl/) – 返回一个 map 容器可以容纳的最大元素数。
*   [`upper_bound()`](https://www.geeksforgeeks.org/map-upper_bound-function-in-c-stl/) – 返回第一个元素的迭代器，该元素相当于映射的键值为“g”的元素，或者肯定会在映射中的键值为“g”的元素之后
*   [`operator=`](https://www.geeksforgeeks.org/map-operator-in-c-stl/) – 将容器的内容分配给不同的容器，替换其当前内容。
*   [`lower_bound()`](https://www.geeksforgeeks.org/map-lower_bound-function-in-c-stl/) – 返回第一个元素的迭代器，该迭代器相当于映射的键值为‘g’的元素，或者在映射中肯定不会位于键值为‘g’的元素之前。
*   [`emplace_hint()`](https://www.geeksforgeeks.org/map-emplace_hint-function-in-c-stl/) – 用给定的提示将键及其元素插入到 map 容器中。
*   [`value_comp()`](https://www.geeksforgeeks.org/map-value_comp-in-c-stl/) – 返回确定地图中元素排序方式的对象(默认为“<”)。
*   [`key_comp()`](https://www.geeksforgeeks.org/map-key_comp-function-in-c-stl/) – 返回决定地图中元素排序方式的对象(默认为<)。
*   [`size()`](https://www.geeksforgeeks.org/mapsize-c-stl/) – 返回地图中的元素个数。
*   [`empty()`](https://www.geeksforgeeks.org/mapempty-c-stl/) – 返回 map 是否为空。
*   [`begin()`](https://www.geeksforgeeks.org/mapbegin-end-c-stl/) 和 [`end()`](https://www.geeksforgeeks.org/mapbegin-end-c-stl/) – `begin()`返回映射中第一个元素的迭代器。`end()` 返回映射中最后一个元素之后的理论元素的迭代器
*   [`operator[]`](https://www.geeksforgeeks.org/map-operator-cpp-stl/) – 该运算符用于引用运算符内部给定位置的元素。
*   [`clear()`](https://www.geeksforgeeks.org/mapclear-c-stl/) – 从贴图中移除所有元素。
*   [`at()`](https://www.geeksforgeeks.org/mapat-mapswap-c-stl/) 和 [`swap()`](https://www.geeksforgeeks.org/mapat-mapswap-c-stl/) – `at()`函数用于返回对与键 k 相关联的元素的引用，`swap()` 函数用于交换两个映射的内容，但是映射必须是相同的类型，尽管大小可能不同。

## [地图上最近的文章](https://www.geeksforgeeks.org/tag/cpp-map/)

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论。