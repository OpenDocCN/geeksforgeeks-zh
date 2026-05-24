# c++ 中运算符重载打印矢量、映射、对、..

> 原文:[https://www . geesforgeks . org/operator-overloading-CPP-print-contents-vector-map-pair/](https://www.geeksforgeeks.org/operator-overloading-cpp-print-contents-vector-map-pair/)

[运算符重载](https://www.geeksforgeeks.org/operator-overloading-c/)是面向对象编程的特征之一，它赋予运算符对用户定义的操作数(对象)进行操作的额外能力。
**我们可以利用这个特性，在竞争性编程中专门调试代码**。我们需要做的就是重载流插入操作符(详见[这篇](https://www.geeksforgeeks.org/operator-overloading-c/)文章)**<<**来打印向量、地图、集合、对等类。例如，

**[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)**

```cpp
// C++ program to print vector objects
// by overloading "<<" operator
#include <iostream>
#include <vector>
using namespace std;

// C++ template to print vector container elements
template <typename T>
ostream& operator<<(ostream& os, const vector<T>& v)
{
    os << "[";
    for (int i = 0; i < v.size(); ++ i) {
        os << v[i];
        if (i != v.size() - 1)
            os << ", ";
    }
    os << "]\n";
    return os;
}

// Driver code
int main()
{
    vector<int> vec{ 4, 2, 17, 11, 15 };

    // Printing the elements directly
    cout << vec;

    return 0;
}
```

```cpp
Output
[4, 2, 17, 11, 15]

```

**[设置](https://www.geeksforgeeks.org/set-in-cpp-stl/)**

```cpp
// C++ program to print set elements
// by overloading "<<" operator
#include <iostream>
#include <set>
using namespace std;

// C++ template to print set container elements
template <typename T>
ostream& operator<<(ostream& os, const set<T>& v)
{
    os << "[";
    for (auto it : v) {
        os << it;
        if (it != *v.rbegin())
            os << ", ";
    }
    os << "]\n";
    return os;
}

// Driver code
int main()
{
    set<int> st{ 4, 2, 17, 11, 15 };
    cout << st;
    return 0;
}
```

```cpp
Output
[2, 4, 11, 15, 17]

```

**[地图](https://www.geeksforgeeks.org/map-associative-containers-the-c-standard-template-library-stl/)**

```cpp
// C++ program to print map elements
// by overloading "<<" operator
#include <iostream>
#include <map>
using namespace std;

// C++ template to print map container elements
template <typename T, typename S>
ostream& operator<<(ostream& os, const map<T, S>& v)
{
    for (auto it : v) 
        os << it.first << " : " 
           << it.second << "\n";

    return os;
}

// Driver code
int main()
{
    map<char, int> mp;
    mp['b'] = 3;
    mp['d'] = 5;
    mp['a'] = 2;

    cout << mp;
}
```

```cpp
Output
a : 2
b : 3
d : 5

```

**[配对](https://www.geeksforgeeks.org/pair-in-cpp-stl/)**

```cpp
// C++ program to print pair<> class
// by overloading "<<" operator
#include <iostream>
using namespace std;

// C++ template to print pair<>
// class by using template
template <typename T, typename S>
ostream& operator<<(ostream& os, const pair<T, S>& v)
{
    os << "(";
    os << v.first << ", " 
       << v.second << ")";
    return os;
}

// Driver code
int main()
{
    pair<int, int> pi{ 45, 7 };
    cout << pi;
    return 0;
}
```

```cpp
Output
(45, 7)

```

从上面我们可以看到，打印或调试将变得更加容易，因为我们不需要为循环或**打印**语句写下额外的**。我们只需要在 cout 的插入操作符“< <”之后写下具体的容器名称。
**练习:**现在让我们根据您的要求为其他容器类设计您自己的带有操作符重载的模板。**

本文由 [Shubham Bansal](https://www.quora.com/profile/Shubham-Bansal-209) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。