# 是 C++ 中的 inite()函数

> 原文:[https://www.geeksforgeeks.org/isfinite-function-in-c/](https://www.geeksforgeeks.org/isfinite-function-in-c/)

isfinite()函数是 C++ 中的内置函数，用于确定给定值是否有限。有限值是既不是无穷大也不是 NAN 的值。如果数字是有限的，那么函数返回 1，否则返回 0。
**语法:**

```cpp
bool isfinite(float x);  

or,
bool isfinite(double x);

or,  
bool isfinite(long double x); 
```

**参数:**该功能只取一个参数![x ](img/13e9d3845c08cedde027ce1766044189.png "Rendered by QuickLaTeX.com")。它表示浮点数。
**返回:**如果数字是无穷大或 NAN，则返回 0，否则如果数字是有限的，则返回 1。
下面的程序说明了 C++ 中的 isfinite()函数:
**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// isfinite() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    float x = 19.0;

    cout<<"The value of x is = "<< x << endl;

    // Here function check whether 19 is finite or not
    // if yes function returns 1, else 0
    cout<<"isfinite(x) = "<<isfinite(x);

    return 0;
}
```

**Output:** 

```cpp
The value of x is = 19
isfinite(x) = 1
```

**节目 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// isfinite() function

#include <bits/stdc++.h>
using namespace std;

int main()
{
    float x=9.6/0.0;

    cout<<"The value of x is = "<< x << endl;

    cout<<"isfinite(x) = "<<isfinite(x);

    return 0;
}
```

**Output:** 

```cpp
The value of x is = inf
isfinite(x) = 0
```

**节目 3:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate the
// isfinite() function

#include <bits/stdc++.h>
using namespace std;

int main()
{  
    // Value is NAN
    double x=0.0/0.0;

    cout<<"Value of x is = "<< x << endl;

    cout<<"isfinite(x) = "<<isfinite(x);

    return 0;
}
```

**Output:** 

```cpp
Value of x is = -nan
isfinite(x) = 0
```