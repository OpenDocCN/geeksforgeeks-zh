# VS 代码|用 C++ 构建、运行和调试

> 原文:[https://www . geesforgeks . org/vs-code-build-run-debug-in-c/](https://www.geeksforgeeks.org/vs-code-build-run-and-debug-in-c/)

在本文中，我们将讨论断点调试所需的 [VS 代码设置](https://www.geeksforgeeks.org/how-to-setup-competitive-programming-in-visual-studio-code-for-c/)。首先创建一个配置 VS 代码的文件 **launch.json** ，在[调试过程](https://www.geeksforgeeks.org/software-engineering-debugging/)开始时启动 [GDB 调试器](https://www.geeksforgeeks.org/gdb-step-by-step-introduction/)。然后创建一个文件 **tasks.json** ，告诉 VS Code [如何构建(编译)程序](https://www.geeksforgeeks.org/compile-32-bit-program-64-bit-gcc-c-c/)。最后，对控制台设置进行一些更改，并实现构建和调试。

**<u>程序</u> :**
下面是演示目的的代码:

## C++

```cpp
// C++ program to find the value of
// the pow(a, b) iteratively
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    int a, b, pow = 1;

    // Input two numbers
    cin >> a >> b;

    // Iterate till b from 1
    for (int i = 1; i <= b; i++) {
        pow = pow * a;
    }

    // Print the value
    cout << pow;
}
```