# c++ 中的 CIN

> 原文:[https://www.geeksforgeeks.org/cin-in-c/](https://www.geeksforgeeks.org/cin-in-c/)

C++ 中的 [cin 对象](https://www.geeksforgeeks.org/basic-input-output-c/)是类 [iostream](https://www.geeksforgeeks.org/c-stream-classes-structure/) 的对象。它用于接受来自标准输入设备(即键盘)的输入。它与标准的 C 输入流 stdin 相关联。[提取操作符(> > )](https://www.geeksforgeeks.org/manipulators-in-c-with-examples/) 与对象 cin 一起用于读取输入。提取操作符从使用键盘输入的对象 cin 中提取数据。

**程序 1:**

下面是实现 cin 对象的 C++ 程序:

## C++

```cpp
// C++ program to demonstrate the
// cin object
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    string s;

    // Take input using cin
    cin >> s;

    // Print output
    cout << s;

    return 0;
}
```