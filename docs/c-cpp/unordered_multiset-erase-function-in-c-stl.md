# c++ STL 中的无序 _ 多集擦除()函数

> 原文:[https://www . geesforgeks . org/unordered _ multist-erase-function-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-erase-function-in-c-stl/)

unordered_multiset::erase()函数是 C++ STL 中的一个内置函数，用于移除单个元素或具有确定值的所有元素，或者从开始(包含)到结束(排除)的一系列元素。这将通过移除的元素数量来减小容器的大小。

**语法**:

> 1.  Out-of-order _ multi-set _name.erase (iterator position)
> 2.  Out-of-order _ multi-set _name.erase (iterator starts and iterator ends)
> 3.  无序 _ 多集 _name.erase(键值)

**参数**:该功能有三个版本。

1.  第一个以迭代器为参数，删除该位置的元素。
2.  第二个版本采用两个迭代器(比如开始和结束)采用两个迭代器作为参数，并删除范围[开始，结束]中的所有元素。
3.  第三个版本将键值作为参数，并删除多集中该值的所有元素。

**返回值**:上面语法所示的函数的第一个和第二个版本在最后一个被擦除的元素之后立即返回一个迭代器。第三个版本返回擦除的元素数量。

以下程序说明了无序 _ 多集::擦除()功能:
**程序 1** :

```cpp
// C++ program to illustrate the
// unordered_multiset::erase() function

#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{
    unordered_multiset<int> samplemultiSet;

    // Inserting elements
    samplemultiSet.insert(10);
    samplemultiSet.insert(5);
    samplemultiSet.insert(15);
    samplemultiSet.insert(20);
    samplemultiSet.insert(25);
    samplemultiSet.insert(10);
    samplemultiSet.insert(15);
    samplemultiSet.insert(20);

    // Erases a particular element by its position
    samplemultiSet.erase(samplemultiSet.begin());

    // Displaying the set after removal
    for (auto it = samplemultiSet.begin(); 
                    it != samplemultiSet.end(); it++) 
    {
        cout << *it << " ";
    }

    // erases a range of elements, 
    // here all the elements
    samplemultiSet.erase(samplemultiSet.begin(), 
                              samplemultiSet.end());

    cout << "\nMultiSet size: " << samplemultiSet.size();

    return 0;
}
```

**Output:**

```cpp
10 10 15 15 20 20 25 
MultiSet size: 0

```

**程序 2** :

```cpp
// C++ program to illustrate the
// unordered_multiset::erase() function

#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{
    unordered_multiset<int> samplemultiSet;

    // Inserting elements
    samplemultiSet.insert(10);
    samplemultiSet.insert(5);
    samplemultiSet.insert(15);
    samplemultiSet.insert(20);
    samplemultiSet.insert(25);
    samplemultiSet.insert(10);
    samplemultiSet.insert(15);
    samplemultiSet.insert(20);

    // Erases all elements of value 10
    samplemultiSet.erase(10);

    // Displaying the set after removal
    for (auto it = samplemultiSet.begin(); 
                it != samplemultiSet.end(); it++) 
    {
        cout << *it << " ";
    }

    return 0;
}
```

**Output:**

```cpp
5 15 15 20 20 25

```