# is_fundamental 模板在 C++ 中

> 原文: [https://www.geeksforgeeks.org/is_fundamental-template-in-c/](https://www.geeksforgeeks.org/is_fundamental-template-in-c/)

C++ STL 的 `is_fundamental` 模板用于检查类型是否为基本类型。它返回一个显示相同内容的布尔值。

## 语法

```cpp
template <class T> struct is_fundamental;
```

## 参数

本模板接受单个参数 `T`（类型特征类），检查 `T` 是否为基本类型。

## 返回值

该模板返回如下所示的布尔值：

*   **True**：如果类型是基本类型。
*   **False**：如果类型是非基本类型。

下面的程序说明了 C++ STL 中的 `is_fundamental` 模板：

### 程序 1

```cpp
// C++ program to illustrate
// is_fundamental template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
class GFG {
};

int main()
{
    cout << boolalpha;
    cout << "is_fundamental:"
         << '\n';
    cout << "GFG :"
         << is_fundamental<GFG>::value
         << '\n';
    cout << "int :"
         << is_fundamental<int>::value
         << '\n';
    cout << "int& :"
         << is_fundamental<int&>::value
         << '\n';
    cout << "int* :"
         << is_fundamental<int*>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_fundamental:
GFG :false
int :true
int& :false
int* :false
```

### 程序 2

```cpp
// C++ program to illustrate
// is_fundamental template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << boolalpha;
    cout << "is_fundamental:"
         << '\n';
    cout << "float:"
         << is_fundamental<float>::value
         << '\n';
    cout << "float&:"
         << is_fundamental<float&>::value
         << '\n';
    cout << "float*:"
         << is_fundamental<float*>::value
         << '\n';
    cout << "double:"
         << is_fundamental<double>::value
         << '\n';
    cout << "double&:"
         << is_fundamental<double&>::value
         << '\n';
    cout << "double*:"
         << is_fundamental<double*>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_fundamental:
float:true
float&:false
float*:false
double:true
double&:false
double*:false
```

### 程序 3

```cpp
// C++ program to illustrate
// is_fundamental template

#include <iostream>
#include <type_traits>
using namespace std;

// main program
int main()
{
    cout << boolalpha;
    cout << "is_fundamental:"
         << '\n';
    cout << "char:"
         << is_fundamental<char>::value
         << '\n';
    cout << "char&:"
         << is_fundamental<char&>::value
         << '\n';
    cout << "char*:"
         << is_fundamental<char*>::value
         << '\n';
    cout << "void :"
         << is_fundamental<void>::value
         << '\n';

    return 0;
}
```

**Output:**

```cpp
is_fundamental:
char:true
char&:false
char*:false
void :true
```