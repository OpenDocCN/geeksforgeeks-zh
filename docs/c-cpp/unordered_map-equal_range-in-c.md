# c++ 中无序 _ 映射相等 _ 范围

> 原文:[https://www . geesforgeks . org/unordered _ map-equal _ range-in-c/](https://www.geeksforgeeks.org/unordered_map-equal_range-in-c/)

无序 _map::equal_range()是 C++ STL 中的一个内置函数，用于返回一个范围的边界，该范围包含容器中的所有元素，其关键字与 k 比较相等。无序 _map 容器是关键字唯一的容器，该范围最多包含一个元素。范围由两个迭代器定义，

*   第一个指向范围的第一个元素。
*   第二个指向范围的最后一个元素。

**参数:**该功能接受单参数*键*，用于保存待比较的数值。

**返回值:**它返回一对包含一对定义所需范围的迭代器。其中它的成员是 pair::first 和 pair::second。第一个是范围下限的迭代器，第二个是范围上限的迭代器。范围中的元素是这两个迭代器之间的元素，包括第一对，但不包括第二对。

下面的程序说明了 C++ STL 中的无序 _map::equal_range()函数:

**例 1:**

```cpp
// C++ program to implement 
// unordered_map::equal_range() function
#include <iostream>
#include <unordered_map>
using namespace std;

// main program
int main()
{
    unordered_map <int, int> map = { { 1, 3 }, 
                                     { 1, 2 }, 
                                     { 3, 1 }, 
                                     { 2, 3 } };
    for (int j = 1; j <= 3; j++) {
        auto range = map.equal_range(j);

        //'auto' is a keyword
        for (auto i = range.first; i != range.second; i++) {

            // iterates first to last
            cout << "first : " << i->first;
            cout << "\nsecond : " << i->second << endl
                << endl;
        }
    }
}
```

**Output:**

```cpp
first : 1
second : 3

first : 2
second : 3

first : 3
second : 1

```

**程序 2:**

```cpp
// C++ program to search 'unordered map' container
#include <iostream>
#include <unordered_map>
using namespace std;

// Rename 'unordered_map<int, char>' as 'gfg'
typedef unordered_map<char, char> gfg;

int main()
{
    // 'g' is object
    gfg g;

    // Container values
    // Contents are look like [a, b] [c, d] [e, f]
    g.insert(gfg::value_type('a', 'b'));
    g.insert(gfg::value_type('b', 'd'));
    g.insert(gfg::value_type('e', 'f'));

    // Look into the syntax part above
    // here 'f' is key
    pair<gfg::iterator, gfg::iterator> p1 = g.equal_range('f');

    // 'f' is not exits, so no output for 'f'
    cout << "search for 'f' :";
    for (; p1.first != p1.second; ++ p1.first) {
        cout << p1.first->first << ", " << p1.first->second << endl;
    }

    // Successful search
    // Here 'a' is key
    p1 = g.equal_range('a');

    // 'a' is exits, so it searched successfully
    cout << "\nsearch for 'a' : [";
    for (; p1.first != p1.second; ++ p1.first) {
        cout << p1.first->first << ", " << p1.first->second << "]";
    }

    return 0;
}
```

**Output:**

```cpp
search for 'f' :
search for 'a' : [a, b]

```

**复杂度:**

*   **平均情况:**用 k 键元素个数线性，为常数。
*   **最差情况:**容器尺寸线性。