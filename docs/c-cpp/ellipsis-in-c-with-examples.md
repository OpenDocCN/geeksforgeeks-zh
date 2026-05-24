# c++ 中的省略号，附示例

> 原文:[https://www.geeksforgeeks.org/ellipsis-in-c-with-examples/](https://www.geeksforgeeks.org/ellipsis-in-c-with-examples/)

**省略号** 在 [中 C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 允许 [函数](https://www.geeksforgeeks.org/functions-in-c/) 接受不确定数量的参数。它就是也就是变量自变量列表。省略号告诉编译器不要检查函数应该接受的参数类型和数量，这允许用户传递变量参数列表。默认情况下，f 函数只能采用函数预先已知的固定数量的参数。用户不能传递可变数量的参数。

**程序 1:**

下面是给出编译错误的代码:

## 【c++

```cpp
// C++ program to demonstrate the
// compilation error as max function
// doesn't take more than 2 arguments
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    // Below Line will given Compilation
    // Error as 4 arguments are passed
    // instead of 2
    int l = max(4, 5, 6, 7);
    cout << l;
    return 0;
}
```