# imag()函数在 C++ 中

> 原文:[https://www.geeksforgeeks.org/imag-function-in-c/](https://www.geeksforgeeks.org/imag-function-in-c/)

**imag()** 功能在**复杂的**头文件中定义。imag()函数用来求复数的虚部。

**语法:**

```cpp
template<class T> T 
    imag(const complex<T>& z);

```

**参数:**该方法取一个强制参数 **z:** ，代表给定的复数。

**返回:**返回复数的**虚部**。

以下程序说明了上述功能

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of imag() function.

#include <bits/stdC++.h>
using namespace std;

// Driver function
int main()
{

    // defines the complex number: (20.3 + 4.9i)
    complex<double> imagpart(20.3, 4.9);

    // print the complex number
    cout << "Complex Number = "
         << imagpart << endl;

    // prints the imag part using the imag function
    cout << "Imag part of the complex number is ="
         << imag(imagpart) << endl;

    return 0;
}
```

**Output:**

```cpp
Complex Number = (20.3,4.9)
Imag part of the complex number is =4.9

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of imag() function.

#include <bits/stdC++.h>
using namespace std;

// driver function
int main()
{
    // defines the complex number: (2 + 2i)
    complex<double> imagpart(2, 2);

    // print the complex number
    cout << "Complex Number = "
         << imagpart << endl;

    // prints the imag part using the imag function
    cout << "Imag part of the complex number is ="
         << imag(imagpart) << endl;

    return 0;
}
```

**Output:**

```cpp
Complex Number = (2,2)
Imag part of the complex number is =2

```