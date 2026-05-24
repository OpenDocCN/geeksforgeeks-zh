# c++ 中 iomanip setprecision()函数示例

> 原文:[https://www . geesforgeks . org/iomanip-set precision-function-in-c-with-examples/](https://www.geeksforgeeks.org/iomanip-setprecision-function-in-c-with-examples/)

C++ 中 **iomaip 库**的 **setprecision()** 方法用于根据指定为该方法参数的精度设置 ios 库浮点精度。

**语法:**

```cpp
setprecision(int n)
```

**参数:**该方法接受 **n** 作为参数，该参数是要设置浮点精度对应的整数参数。

**返回值:**这个方法不返回任何东西。它只充当流操纵器。

**例 1:**

## C++

```cpp
// C++ code to demonstrate
// the working of setprecision() function

#include <iomanip>
#include <ios>
#include <iostream>

using namespace std;

int main()
{

    // Initializing the decimal
    double num = 3.142857142857;

    cout << "Before setting the precision: \n"
         << num << endl;

    // Using setprecision()
    cout << "Setting the precision using"
         << " setprecision to 5: \n"
         << setprecision(5);

    cout << num << endl;

    // Using setprecision()
    cout << "Setting the precision using"
           << " setprecision to 9 : \n "
         << setprecision(9);

    cout << num << endl;

    return 0;
}
```

**Output:** 

```cpp
Before setting the precision: 
3.14286
Setting the precision using setprecision to 5: 
3.1429
Setting the precision using setprecision to 9: 
3.14285714
```

**例 2:**

## C++

```cpp
// C++ code to demonstrate
// the working of setprecision() function

#include <iomanip>
#include <ios>
#include <iostream>

using namespace std;

int main()
{

    // Initializing the decimal
    double num = 3.14;

    cout << fixed;

    cout << "Before setting the precision: \n"
         << num << endl;

    // Using setprecision()
    cout << "Setting the precision using"
         << " setprecision to 5: \n"
         << setprecision(5);

    cout << num << endl;

    // Using setprecision()
    cout << "Setting the precision using"
         << " setprecision to 9: \n"
         << setprecision(9);

    cout << num << endl;
    return 0;
}
```

**Output:** 

```cpp
Before setting the precision: 
3.140000
Setting the precision using setprecision to 5: 
3.14000
Setting the precision using setprecision to 9: 
3.140000000
```

**参考:**T2http://www.cplusplus.com/reference/iomanip/setprecision/