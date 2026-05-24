# c++ STL 中的多映射键 _ comp

> 原文:[https://www.geeksforgeeks.org/multimap-key_comp-in-c-stl-2/](https://www.geeksforgeeks.org/multimap-key_comp-in-c-stl-2/)

这是 C++ 的**标准模板库(STL)** 的一部分。要使用这个 **STL** ，使用**命名空间:std** 并在程序中包含**【映射】**头文件。
返回比较键的**函数对象**或**比较对象**或**排序委托**，这是这个容器的构造函数参数的副本。
是一个函数**指针**或者一个**对象**取两个同类型的参数作为元素键，决定容器中元素的顺序。

**语法:**

> key _ compare key _ comp()；

这里**键 _ 比较**是*比较对象*的类型，与容器相关联。

**参数:**

> 它不接受任何参数。

**返回:**

> 返回键比较函数**对象**或**排序委托**，在*多映射*中定义为其第三个模板参数的别名。

以下是 multimap::key_comp 的示例:

```cpp
// c++ program to show
// the use of multimap::key_comp
#include <iostream>
#include <map>
using namespace std;

// Driver code
int main()
{
    multimap<char, int> m1;

    //'comp' works as a variable
    multimap<char, int>::key_compare comp = m1.key_comp();

    // set the values of the pairs
    m1.insert(make_pair('a', 10));
    m1.insert(make_pair('b', 20));
    m1.insert(make_pair('b', 30));
    m1.insert(make_pair('c', 40));

    // key value of last element
    char h = m1.rbegin()->first;
    multimap<char, int>::iterator i = m1.begin();
    do {
        cout << (*i).first << " = " << (*i).second << '\n';
    } while (comp((*i++).first, h));

    return 0;
}
```

**Output:**

```cpp
a = 10
b = 20
b = 30
c = 40

```