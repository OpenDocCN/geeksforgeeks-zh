# boost::type _ traits::is _ array Template 在 C++ 中

> 原文:[https://www . geeksforgeeks . org/boottype _ traitsis _ array-template-in-c/](https://www.geeksforgeeks.org/boosttype_traitsis_array-template-in-c/)

Boost C++ 库的 **std::boost::is_array** 模板，用于检查给定类型是否为数组类型。它返回一个显示相同内容的布尔值。

**头文件:**

```cpp
#include "boost/type_traits/is_array.hpp" 
or 
#include "boost/type_traits.hpp"

```

**模板类:**

```cpp
template <class T>
struct is_array : public true_type-or-false_type {};

```

如果 T 是数组类型，则从 true_type 继承，否则从 false_type 继承。

**语法:**

```cpp
boost::integral_constant ::value
boost::integral_constant ::value_type
boost::integral_constant ::type

```

**参数:**该模板接受单个参数 **T(Trait 类)**检查 T 是否为指针类型。

**接受的论点:**

```cpp
typename T
volatile T []
const volatile T []
const T []
T []
const volatile T[N]
volatile T [N]
const T [N]
T [N]

```

**返回值:**该模板返回如下所示的布尔值:

*   **真:**如果类型是指针值。
*   **False:** 如果类型不是指针值。

下面的程序说明了**STD::boost::type _ traits::is _ array**模板:
T3】程序 1:

```cpp
// C++ program to illustrate std::is_array template
#include <bits/stdc++.h>
#include <boost/type_traits/is_array.hpp>
#include <boost/typeof/typeof.hpp>
using namespace std;

// Main Program
int main()
{
    cout << "is_array: \n";
    cout << "int[]: "
         << boost::is_array<int[]>::value
         << "\n";
    cout << "char[]: "
         << "boost::is_array<char[]>::value"
         << "\n";

    cout << "double[20]: "
         << boost::is_array<double[20]>::value
         << "\n";
    cout << "float[30]: "
         << boost::is_array<float[30]>::value
         << "\n";

    cout << "bool[][6]: "
         << boost::is_array<bool[][6]>::value
         << "\n";
    cout << "long[56][34][98]: "
         << boost::is_array<long[56][34][98]>::value
         << "\n";

    bool a[98];

    cout << "bool a[98]: "
         << boost::is_array<decltype(a)>::value
         << "\n";

    char c[0];

    cout << "char c[0]: "
         << boost::is_array<decltype(c)>::value
         << "\n";

    return 0;
}
```

**Output:**

```cpp
is_array: 
int[]: 1
char[]: boost::is_array::value
double[20]: 1
float[30]: 1
bool[][6]: 1
long[56][34][98]: 1
bool a[98]: 1
char c[0]: 0

```

**程序 2:**

```cpp
// C++ program to illustrate std::is_array template
#include <bits/stdc++.h>
#include <boost/type_traits/is_array.hpp>
#include <boost/typeof/typeof.hpp>
using namespace std;

// A Structure
struct sturec {
    int x, y;
    float a, b;
    long t[90];
};

// A Class
class student {
private:
    string name;
    int roll_no;

public:
    student(string name, int roll_no);
    string studentName(int roll_no);
};

// Parameterized Constructor
student::student(string name, int roll_no)
{
    this->name = name;
    this->roll_no = roll_no;
}

// Function that return the name
// of the student
string student::studentName(int roll_no)
{
    return this->name;
}

// Main Program
int main()
{
    cout << "is_array: \n";

    sturec s;
    sturec p[3];

    cout << "instance of structure: "
         << boost::is_array<decltype(s)>::value
         << "\n";
    cout << "array of structure: "
         << boost::is_array<decltype(p)>::value
         << "\n";

    // Instance of Class
    student S("GeeksforGeeks", 11840520);
    cout << "instance of a class: "
         << boost::is_array<decltype(S)>::value
         << "\n";

    // Array of Class
    student a[3] = {
        { "Abc Def", 11840820 },
        { "Xyz Xyz", 11840220 },
        { "ABcd Gfgh", 11840950 }
    };

    cout << "array of a class: "
         << boost::is_array<decltype(a)>::value
         << "\n";

    return 0;
}
```

**Output:**

```cpp
is_array: 
instance of structure: 0
array of structure: 1
instance of a class: 0
array of a class: 1

```