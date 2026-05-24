# VS 代码| c++ 编译运行

> 原文:[https://www.geeksforgeeks.org/vs-code-compile-and-run-in-c/](https://www.geeksforgeeks.org/vs-code-compile-and-run-in-c/)

在这篇文章中，我们将学习如何在 **VS 代码**中编译和运行 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 程序。有两种方法，你可以根据自己的方便使用其中任何一种。需要注意的是，大多数有竞争力的程序员使用 C++，因此程序的编译和执行需要快速完成。本文讨论的一些方法几乎使[编译](https://www.geeksforgeeks.org/compiling-a-c-program-behind-the-scenes/)和执行的过程自动化。

**<u>程序</u> :**
下面让代码演示编译和执行:

## C++

```cpp
// C++ program to take the input of
// two numbers and prints its sum
#include <bits/stdc++.h>
using namespace std;

// Driver Code
int main()
{
    int a, b;

    // Input two numbers
    cin >> a >> b;

    // Find the sum
    int sum = a + b;

    // Print the sum
    cout << sum;

    return 0;
}
```