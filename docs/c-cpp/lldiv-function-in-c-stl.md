# c++ STL 中的 lldiv()函数

> 原文:[https://www.geeksforgeeks.org/lldiv-function-in-c-stl/](https://www.geeksforgeeks.org/lldiv-function-in-c-stl/)

**lldiv()** 是 C++ STL 中的一个内置函数，它给出了两个数除法的商和余数。

**语法**:

```cpp
lldiv(n, d)
```

**参数**:该功能接受两个强制参数，描述如下:

*   **n:** 指定分红。数据类型可以是 long long 或 long int。
*   **d:** 指定除数。数据类型可以是 long long 或 long int。

**返回值**:该函数返回一个类型为 **lldiv_t** 的结构，该结构由两个成员组成:**和 rem** ，其中*为商， *rem* 为余数。该结构定义如下:*

```cpp
*struct lldiv_t {
    long long quot;
    long long rem;
};*
```

*以下程序说明了上述功能:*

***程序 1** :*

```cpp
*// C++ program to illustrate the
// lldiv() function
#include <cstdlib>
#include <iostream>
using namespace std;

int main()
{
    long long n = 1000LL;
    long long d = 50LL;

    lldiv_t result = lldiv(n, d);

    cout << "Quotient of " << n << "/" << d
         << " = " << result.quot << endl;

    cout << "Remainder of " << n << "/" << d
         << " = " << result.rem << endl;

    return 0;
}*
```

***Output:**

```cpp
Quotient of 1000/50 = 20
Remainder of 1000/50 = 0

```* 

***程序 2** :*

```cpp
*// C++ program to illustrate
// the lldiv() function
#include <cstdlib>
#include <iostream>
using namespace std;

int main()
{
    long long int n = 251987LL;
    long long int d = 68LL;

    lldiv_t result = lldiv(n, d);

    cout << "Quotient of " << n << "/" << d
         << " = " << result.quot << endl;
    cout << "Remainder of " << n << "/" << d
         << " = " << result.rem << endl;

    return 0;
}*
```

***Output:**

```cpp
Quotient of 251987/68 = 3705
Remainder of 251987/68 = 47

```*