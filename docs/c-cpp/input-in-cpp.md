# c++ 中的输入

> 原文:[https://www.geeksforgeeks.org/input-in-cpp/](https://www.geeksforgeeks.org/input-in-cpp/)

C++ 中的 [cin 对象](https://www.geeksforgeeks.org/basic-input-output-c/)用于接受来自标准输入设备即键盘的输入。这是班级的实例[是团队](https://www.geeksforgeeks.org/c-stream-classes-structure/)。它与标准的 C 输入流 stdin 相关联。[提取操作符(> > )](https://www.geeksforgeeks.org/overloading-stream-insertion-operators-c/) 与对象 cin 一起用于读取输入。提取操作符从使用键盘输入的对象 cin 中提取数据。

**程序 1:**

下面是实现 cin 对象从用户处获取输入的 C++ 程序:

## C++

```cpp
// C++ program to demonstrate the
// cin object
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    int i;

    // Take input using cin
    cin >> i;

    // Print output
    cout << i;

    return 0;
}
```