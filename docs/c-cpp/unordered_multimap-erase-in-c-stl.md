# c++ STL 中无序 _ 多映射擦除

> 原文:[https://www . geesforgeks . org/unordered _ multimap-erase-in-c-STL/](https://www.geeksforgeeks.org/unordered_multimap-erase-in-c-stl/)

unordered_multimap::erase()是 C++ STL 中的一个内置函数，它通过位置和键从给定的范围中移除元素。这个函数在 C++ STL 中有三种变体。
c++ 中对于无序 _ 多映射有以下几种类型的 erase()函数。

1.  **按位置**:它通过给定的位置从无序多映射中移除元素，并返回一个迭代器，该迭代器指向被擦除的最后一个元素之后的位置。
2.  **按键:**按键移除元素。它返回已擦除的元素数量。
3.  **按范围:**取迭代器的第一个和最后一个，去掉它们之间的所有元素，包括第一个但不包括最后一个。它返回一个迭代器，指向紧接着最后一个被删除元素的位置。

**语法:**

> 1.  Iterator Erase (Iterator Position)
> 2.  Erase size (key_type & k)
> 3.  Iterator erasure (iterator first, iterator last);

下面的程序解释了上述功能。
**例 1**

```cpp
// C++ program to illustrate the
// unordered_multimap::erase() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration of unordered_multimap
    unordered_multimap<char, int> sample;

    // inserts element
    sample.insert({ 'a', 2 });
    sample.insert({ 'b', 4 });
    sample.insert({ 'c', 8 });
    sample.insert({ 'd', 10 });
    sample.insert({ 'c', 4 });
    sample.insert({ 'e', 4 });
    sample.insert({ 'f', 4 });
    cout << " Elements of multimap are : \n";
    for (auto& x : sample)
        cout << x.first << " : " << x.second << endl;

    // delete element by position
    sample.erase(sample.begin());

    // print after delete by position
    cout << " Elements of multimap after deleting by position are : \n";
    for (auto& x : sample)
        cout << x.first << " : " << x.second << endl;

    // erase by Element
    sample.erase('c');

    // print after delete by element
    cout << " Elements of multimap after deleting by element name : \n";
    for (auto& x : sample)
        cout << x.first << " : " << x.second << endl;

    // erase by range
    sample.erase(sample.find('e'), sample.end());

    // print after delete by range
    cout << " Elements of multimap after deleting by range are : \n";
    for (auto& x : sample)
        cout << x.first << " : " << x.second << endl;
    return 0;
}
```

**Output:**

```cpp
Elements of multimap are : 
f : 4
b : 4
a : 2
c : 4
c : 8
d : 10
e : 4
 Elements of multimap after deleting by position are : 
b : 4
a : 2
c : 4
c : 8
d : 10
e : 4
 Elements of multimap after deleting by element name : 
b : 4
a : 2
d : 10
e : 4
 Elements of multimap after deleting by range are : 
b : 4
a : 2
d : 10

```

**例 2**

```cpp
// C++ program to illustrate the
// unordered_multimap::erase() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // declaration of unordered_multimap
    unordered_multimap<int, int> sample;

    // inserts element
    sample.insert({ 1, 2 });
    sample.insert({ 2, 4 });
    sample.insert({ 3, 8 });
    sample.insert({ 4, 10 });
    sample.insert({ 3, 4 });
    sample.insert({ 5, 4 });
    sample.insert({ 6, 4 });
    cout << " Elements of multimap are : \n";
    for (auto& x : sample)
        cout << x.first << " : " << x.second << endl;

    // delete element by position
    sample.erase(sample.begin());

    // print after delete by position
    cout << " Elements of multimap after deleting by position are : \n";
    for (auto& x : sample)
        cout << x.first << " : " << x.second << endl;

    // erase by Element
    sample.erase(3);

    // print after delete by element
    cout << " Elements of multimap after deleting by element name : \n";
    for (auto& x : sample)
        cout << x.first << " : " << x.second << endl;

    // erase by range
    sample.erase(sample.find(5), sample.end());

    // print after delete by range
    cout << " Elements of multimap after deleting by range are : \n";
    for (auto& x : sample)
        cout << x.first << " : " << x.second << endl;
    return 0;
}
```

**Output:**

```cpp
Elements of multimap are : 
6 : 4
2 : 4
1 : 2
3 : 4
3 : 8
4 : 10
5 : 4
 Elements of multimap after deleting by position are : 
2 : 4
1 : 2
3 : 4
3 : 8
4 : 10
5 : 4
 Elements of multimap after deleting by element name : 
2 : 4
1 : 2
4 : 10
5 : 4
 Elements of multimap after deleting by range are : 
2 : 4
1 : 2
4 : 10

```