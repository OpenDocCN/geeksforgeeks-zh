# 读取整数后读取字符串

> 原文:[https://www . geesforgeks . org/读取整数后读取字符串/](https://www.geeksforgeeks.org/read-a-string-after-reading-an-integer/)

在本文中，我们将讨论如何在读取整数后读取字符串。

**程序 1:**

下面是在输入一个整数 :

## 之后输入一个带有空格的 的程序

```cpp
// C++ program that inputs a string
// with spaces just after taken an
// input of an integer

#include <iostream>
#include <string>
using namespace std;

// Driver Code
int main()
{
    int t = 0;
    cin >> t;

    string s;

    // Taking input with spaces
    getline(cin, s);

    cout << "You entered : "
         << s << "\n";

    return 0;
}
```