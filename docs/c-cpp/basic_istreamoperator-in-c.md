# basic _ is tream::c++ 中的运算符>>

> 原文:[https://www.geeksforgeeks.org/basic_istreamoperator-in-c/](https://www.geeksforgeeks.org/basic_istreamoperator-in-c/)

**basic _ is tream::operator>>**被称为提取运算符。该运算符用于应用于输入字符串。
T3】头文件:T5】

```cpp
<iostream>
```

**语法:**

```cpp
basic_istream& operator>>( int& a );
basic_istream& operator>>( unsigned int& a );
```

**参数:**

*   **a** :表示提取的字符存储的值。

**返回值:****is tream::运算符> >** 返回 basic_istream 对象。
下面是程序说明**STD::basic _ is tream::operator>>:**
程序 1:

## CPP14

```cpp
// C++ code for basic_istream::operator>>
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    // Declare the string "12 12.2 GeeksforGeeks"
    string gfg = "12 12.2 GeeksforGeeks";

    istringstream stream(gfg);
    int a;
    float b;
    bool c;

    stream >> a >> b >> boolalpha >> c;
    cout << "a = " << a << '\n'
         << "b = " << b << '\n'
         << "c = " << boolalpha << c << endl;

    return 0;
}
```

**Output:** 

```cpp
a = 12
b = 12.2
c = false
```

**节目 2:**

## CPP14

```cpp
// C++ code for basic_istream::operator>>
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    // Declare the string "144 0.26 GFG"
    string gfg = "144 0.26 GFG";

    istringstream stream(gfg);
    int a;
    float b;
    bool c;

    stream >> a >> b >> boolalpha >> c;
    cout << "a = " << a << '\n'
         << "b = " << b << '\n'
         << "c = " << boolalpha << c << endl;

    return 0;
}
```

**Output:** 

```cpp
a = 144
b = 0.26
c = false
```

**参考:**T2【http://www . cplusplus . com/Reference/is tream/basic _ is tream/operator % 3E % 3E/T4】