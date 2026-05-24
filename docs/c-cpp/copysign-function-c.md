# c++ 中的 copysign()函数

> 原文:[https://www.geeksforgeeks.org/copysign-function-c/](https://www.geeksforgeeks.org/copysign-function-c/)

**copysign(x，y)** 函数返回数值，数值大小为 x，符号为 y。

**例:**

```cpp
Input : copysign(6, -2)
Output : -6

Input : copysign(-6, 2)
Output : 6

```

**语法:**

```cpp
copysign(x, y);

```

**参数:**

```cpp
x : Value with the magnitude 
y : Value with the sign 

```

**返回:**

```cpp
Returns the value with a magnitude of x
and the sign of y.
Return type follows type casting i.e., 
if If one element is float and second 
element int then it returns float. 

```

下面是上面的实现:

```cpp
// C++ program to return copysign value
#include <bits/stdc++.h>     
using namespace std;     

int main ()
{
    cout << "Magnitude = 6 Sign = -2 " << endl;
    cout << "Copysign(6, -2) = " 
         << copysign(6, -2) << endl;

    cout << endl;

    cout << "Magnitude = -6 Sign = 2 " << endl;
    cout << "Copysign(-6, 2) = " 
         << copysign(-6, 2);

    return 0;
}
```

**输出:**

```cpp
Magnitude = 6  Sign = -2
Copysign(6, -2) = -6

Magnitude = -6  Sign = 2
Copysign(-6, 2) = 6

```