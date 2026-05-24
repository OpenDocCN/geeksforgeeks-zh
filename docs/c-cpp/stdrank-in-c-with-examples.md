# 标准::C++ 中的等级，示例

> 原文:[https://www.geeksforgeeks.org/stdrank-in-c-with-examples/](https://www.geeksforgeeks.org/stdrank-in-c-with-examples/)

**C++ STL** 的 **std::rank** 模板存在于**T12】type _ traits>T5】头文件中。C++ STL 的 **std::rank** 模板用于查找 **T** 类型的 rank。该功能返回类型 **T** 的等级。**

**头文件:**

```cpp
#include<type_traits>

```

**模板类:**

```cpp
template<class T>
struct rank;

template<class T>
inline constexpr
       std::size_t rank_v
        = rank<T>::value;

```

**语法:**

```cpp
std::rank<T>::value

```

**参数:****STD::rank**模板接受单个参数 **T(Trait 类)**并返回其排名。

**返回值:**模板 **std::rank** 返回类型 **T** 的 rank。

下面是演示**标准::等级:**的程序

**程序:**

```cpp
// C++ program to illustrate std::rank
#include <bits/stdc++.h>
#include <type_traits>
using namespace std;

// Driver Code
int main()
{

    cout << "rank of following type:"
         << endl;
    cout << "int: "
         << rank<int>::value
         << endl;

    cout << "int[]: "
         << rank<int[]>::value
         << endl;

    cout << "int[][10]: "
         << rank<int[][10]>::value
         << endl;

    cout << "int[10][10]: "
         << rank<int[10][10]>::value
         << endl;

    return 0;
}
```

**输出:**

```cpp
rank of following type:
int: 0
int[]: 1
int[][10]: 2
int[10][10]: 2

```

**参考:**T2】http://www.cplusplus.com/reference/type_traits/rank/