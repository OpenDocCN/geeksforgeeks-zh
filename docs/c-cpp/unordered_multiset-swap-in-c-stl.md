# c++ STL 中的无序 _ 多集交换()

> 原文:[https://www . geesforgeks . org/unordered _ multist-swap-in-c-STL/](https://www.geeksforgeeks.org/unordered_multiset-swap-in-c-stl/)

**“无序 _ 多集”**的**交换()**方法交换两个容器的内容。它是公共成员函数。该功能:

*   通过**变量**的内容交换容器的内容，该变量是另一个包含相同类型元素但大小可能不同的*无序 _ 多集*对象。
*   在调用这个成员函数之后，这个容器中的元素是那些在调用之前在**变量**中的元素，而**变量**的元素是那些在这个容器中的元素。

**语法:**

```cpp
void swap(unordered_multiset &another_unordered_multiset);
```

**参数:**它接收**另一个 _ 无序 _ 多集**容器对象，其类型与它要交换的容器相同。

**返回:**不返回值。

下面的程序说明了**无序 _ 多集交换()**函数:-

**例 1:**

```cpp
#include <iostream>
#include <string>
#include <unordered_set>

using namespace std;

int main()
{

    // sets the values in two container
    unordered_multiset<string>
        first = { "FOR GEEKS" },
        second = { "GEEKS" };

    // before swap values
    cout << "before swap :- \n";

    cout << "1st container : ";
    for (const string& x : first)
        cout << x << endl;

    cout << "2nd container : ";
    for (const string& x : second)
        cout << x << endl;

    // call swap

    first.swap(second);

    // after swap values
    cout << "\nafter swap :- \n";

    // displaying 1st container
    cout << "1st container : ";
    for (const string& x : first)
        cout << x << endl;

    // displaying 2nd container
    cout << "2nd container : ";
    for (const string& x : second)
        cout << x << endl;

    return 0;
}
```

**Output:**

```cpp
before swap :- 
1st container : FOR GEEKS
2nd container : GEEKS

after swap :- 
1st container : GEEKS
2nd container : FOR GEEKS

```

**例 2:**

```cpp
#include <iostream>
#include <string>
#include <unordered_set>

using namespace std;

int main()
{

    // sets the values in two container
    unordered_multiset<int>
        first = { 1, 2, 3 },
        second = { 4, 5, 6 };

    // before swap values
    cout << "before swap :- \n";

    cout << "1st container : ";
    for (const int& x : first)
        cout << x << " ";
    cout << endl;

    cout << "2nd container : ";
    for (const int& x : second)
        cout << x << " ";
    cout << endl;

    // call swap

    first.swap(second);

    // after swap values
    cout << "\nafter swap :- \n";

    // displaying 1st container
    cout << "1st container : ";
    for (const int& x : first)
        cout << x << " ";
    cout << endl;

    // displaying 2nd container
    cout << "2nd container : ";
    for (const int& x : second)
        cout << x << " ";
    cout << endl;

    return 0;
}
```

**Output:**

```cpp
before swap :- 
1st container : 3 2 1 
2nd container : 6 5 4 

after swap :- 
1st container : 6 5 4 
2nd container : 3 2 1 

```