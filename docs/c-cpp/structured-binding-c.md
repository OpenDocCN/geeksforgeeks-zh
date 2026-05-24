# c++ 中的结构化绑定

> 原文:[https://www.geeksforgeeks.org/structured-binding-c/](https://www.geeksforgeeks.org/structured-binding-c/)

**先决条件:**[c++ 中的元组](https://www.geeksforgeeks.org/tuples-in-c/)

结构化绑定是 C++ 17 的最新特性之一，它将指定的名称绑定到初始值设定项的子对象或元素。简单地说，结构化绑定让我们能够声明从一个元组或结构初始化的多个变量。C++ 17 中结构化绑定的主要目的是使代码清晰易懂。像引用一样，结构化绑定是现有对象 的 ***别名。与引用不同，结构化绑定的类型 ***不一定是引用类型*** 。***

**语法:**

```cpp
auto ref-operator*(optional)*[identifier-list] = expression;

// Or

auto ref-operator*(optional)*[identifier-list]{expression};

// Or

auto ref-operator*(optional)*[identifier-list](expression);

```

**参数:**

*   **自动:**T2】自动
*   **参考操作员:**&或& &
*   **标识符-列表:**逗号分隔的变量名列表。
*   **表达式:**顶层没有逗号运算符的表达式(即赋值表达式)，并且具有数组或非并集类类型。

### **基本类型推演:**

让 **E** 表示 ***初始值设定项表达式*** 的类型。e 要么是 **std::tuple** 的特化，要么是非静态数据成员都可以访问并在 e 的同一个基类中声明的类型。根据 e，结构化绑定声明以三种可能的方式之一执行绑定

*   **情况 1** :如果 E 是数组类型，那么名字绑定到数组元素。
*   **情况 2** :如果 E 是非并集类类型， **tuple_size** 是完整类型，则使用“类 tuple”绑定协议。
*   **情况 3** :如果 E 是非并集类类型但是 **tuple_size** 不是完整类型，那么名字绑定到 E 的公共数据成员

让我们借助一个例子来看看结构绑定相对于元组的优势:
**例 1 :** 在 C++ 98 中

```cpp
#include <bits/stdc++.h>
using namespace std;

// Creating a structure named Point
struct Point {
    int x;
    int y;
};

// Driver code
int main()
{
    Point p = {1, 2};

    int x_coord = p.x;
    int y_coord = p.y;

    cout << "X Coordinate : " << x_coord << endl;
    cout << "Y Coordinate : " << y_coord << endl;

    return 0;
}
```

输出:

```cpp
X Coordinate : 1
Y Coordinate : 2

```

**例 2 :** 在 C++ 11/C++ 14 中

```cpp
#include <bits/stdc++.h>
#include <tuple>
using namespace std;

// Creating a structure named Point
struct Point
{
    int x, y;

    // Default Constructor
    Point() : x(0), y(0) 
    {

    }

    // Parameterized Constructor for Init List
    Point(int x, int y) : x(x), y(y) 
    {

    }
    auto operator()()
    {
        // returns a tuple to make it work with std::tie
        return make_tuple(x, y); 
    }
};

// Driver code
int main()
{
    Point p = {1, 2};
    int x_coord, y_coord;
    tie(x_coord, y_coord) = p();

    cout << "X Coordinate : " << x_coord << endl;
    cout << "Y Coordinate : " << y_coord << endl;

    return 0;
}
```

输出:

```cpp
X Coordinate : 1
Y Coordinate : 2

```

**示例 3 :** 在 C++ 17 中

```cpp
#include <bits/stdc++.h>
using namespace std;

struct Point
{
    int x;
    int y;
};

// Driver code
int main( )
{
    Point p = { 1,2 };

    // Structure binding
    auto[ x_coord, y_coord ] = p;

    cout << "X Coordinate : " << x_coord << endl;
    cout << "Y Coordinate : " << y_coord << endl;

    return 0;
}
```

输出:

```cpp
X Coordinate : 1
Y Coordinate : 2

```

**应用:**结构化绑定可以和数组一起使用，从数组中获取元素。在这种情况下，E 是一个数组类型，因此名称被绑定到数组元素。下面是同样的实现:

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{

    int arr[3] = { 1, 2, 3 };

    // Here, E is an array type, hence the 
    // names are bound to the array elements.
    auto[x, y, z] = arr;

    cout << x << " " << y << " " << z << endl;

    return 0;
}
```

输出:

```cpp
1 2 3

```

**注意:**标识符列表中的标识符数量必须等于数组中的元素数量。如果标识符列表中的标识符数量较少，则可能会出现编译时错误或设计时错误。这意味着我们不能从数组中获取特定的元素集。

使用结构化绑定的一个更实际的例子如下:

```cpp
#include <bits/stdc++.h>
#include <map>
using namespace std;

int main()
{
    // Creating a map with key and value 
    // fields as String
    map<string, string> sites;

    sites.insert({ "GeeksforGeeks", "Coding Resources" });
    sites.insert({ "StackOverflow", "Q-A type" });
    sites.insert({ "Wikipedia", "Resources + References" });

    for (auto & [ key, value ] : sites) 
    {
       cout << key.c_str() << " " << value.c_str() << endl;
    }

    return 0;
}
```

输出:

```cpp
GeeksforGeeks Coding Resources
StackOverflow Q-A type
Wikipedia Resources + References

```

**注意:**限定词如 [const](https://www.geeksforgeeks.org/const-qualifier-in-c/) 和 [volatile](https://www.geeksforgeeks.org/understanding-volatile-qualifier-c-set-1-introduction/) 可以和 type 一起使用，使声明变量为常量或 volatile。

有关结构化绑定的更多详细信息，您可以参考: [P0144R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0144r0.pdf)