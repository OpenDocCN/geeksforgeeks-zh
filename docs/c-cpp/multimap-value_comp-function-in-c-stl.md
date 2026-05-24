# c++ STL 中的 multimap value_comp()函数

> 原文:[https://www . geesforgeks . org/multimap-value _ comp-function-in-c-STL/](https://www.geeksforgeeks.org/multimap-value_comp-function-in-c-stl/)

**multimap::value_comp()** 方法返回一个比较对象，可以用来比较两个元素，得到第一个的键是否在第二个之前。这里第一个对象比较类型 **std::multimap::类型**的对象。此函数对象采用的参数是成员类型*类型*。在**多映射**中定义为**对**的别名。

**语法:**

```cpp
multimap::compared_value value_comp() const;
```

这里**比较 _ 值**是**的一个嵌套类类型**

**参数:**不接受任何参数。

**返回值:**此方法返回*比较对象*，它是成员类型*的对象:multimap::comparated _ Value*，它是一个嵌套类，使用内部比较对象生成适当的比较函数类。

下图程序说明了 multimap value_comp()函数:

```cpp
// C++ program to show
// the use of multimap::value_comp

#include <iostream>
#include <map>
using namespace std;

int main()
{
    multimap<char, int> m;

    // making of pair
    m.insert(make_pair('a', 10));
    m.insert(make_pair('b', 20));
    m.insert(make_pair('c', 30));
    m.insert(make_pair('d', 40));

    pair<char, int> p = *m.rbegin();
    // last element

    multimap<char, int>::iterator i = m.begin();

    do {

        cout << (*i).first
             << " = " << (*i).second
             << '\n';

    } while (m.value_comp()(*i++, p));

    return 0;
}
```

**输出:**

```cpp
a = 10
b = 20
c = 30
d = 40

```