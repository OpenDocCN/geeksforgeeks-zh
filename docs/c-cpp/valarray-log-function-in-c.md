# c++ 中的 valarray log()函数

> 原文:[https://www.geeksforgeeks.org/valarray-log-function-in-c/](https://www.geeksforgeeks.org/valarray-log-function-in-c/)

**log()** 函数在 **valarray** 头文件中定义。此函数用于计算 valarray 中元素值的自然对数。
**语法:**

```cpp
log(varr);

```

**参数:**该函数采用代表 valarray 的强制参数 **varr** 。

**返回:**这个函数返回一个包含所有元素的自然对数的 valarray。

以下程序说明了上述功能:

**实施例 1:-**

```cpp
// C++ program to demonstrate
// example of log() function.

#include<bits/stdc++.h>
using namespace std; 
int main() 
{ 
    // Initializing valarray 
    valarray<double>
 varr = { 1, 2, 3, 4, 5 }; 

    // Declaring new valarray 
    valarray<double> varr1 ; 

    // use of log() function 
    varr1 = log(varr); 

    // Displaying new elements value
    cout << "The new valarray with"
         << " manipulated values is : "
         << endl;

    for (double& x : varr1) {
        cout << x << " ";
    }

    cout << endl;

    return 0;
} 
```

**Output:**

```cpp
The new valarray with manipulated values is : 
0 0.693147 1.09861 1.38629 1.60944

```

**实施例 2:-**

```cpp
// C++ program to demonstrate
// example of log() function.

#include<bits/stdc++.h>
using namespace std; 
int main() 
{ 
    // Initializing valarray 
    valarray<double>
 varr = { -1, 6, 3, 45, 5 }; 

    // Declaring new valarray 
    valarray<double> varr1 ; 

    // use of log() function 
    varr1 = log(varr); 

    // Displaying new elements value
    cout << "The new valarray with"
         << " manipulated values is : "
         << endl;

    for (double& x : varr1) {
        cout << x << " ";
    }

    cout << endl;

    return 0;
} 
```

**Output:**

```cpp
The new valarray with manipulated values is : 
nan 1.79176 1.09861 3.80666 1.60944

```