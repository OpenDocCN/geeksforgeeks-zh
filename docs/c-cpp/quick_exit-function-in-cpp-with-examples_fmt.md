# c++ 中的 `quick_exit()` 函数，示例

> 原文：[https://www.geeksforgeeks.org/quick_exit-function-in-cpp-with-examples/](https://www.geeksforgeeks.org/quick_exit-function-in-cpp-with-examples/)

`quick_exit()` 函数在标准库头文件中定义。`quick_exit()` 函数用于在不完全清理资源的情况下正常终止进程。

*   如果 `val` 为零或 `EXIT_SUCCESS`，程序成功终止。
*   如果值为非零或 `EXIT_FAILURE`，则表示程序未成功终止。这些函数按照其调用顺序的逆序被调用。

## 语法：

```cpp
void quick_exit(int val);
```

## 参数：
该方法取单个参数 `val`，该值为代表程序退出状态的整数值。

## 返回值：
这个函数不返回任何东西。

## 例：
下面的程序说明了 C++ 中的 `quick_exit()` 函数：

```cpp
// c++ program to demonstrate
// example of quick_exit() function.

#include <bits/stdc++.h>
using namespace std;

void function1()
{
    cout << "Exit Function 1" << endl;
}
void function2()
{
    cout << "Exit Function 2" << endl;
}

int main()
{
    // registering function 
    at_quick_exit(function1);
    at_quick_exit(function2);

    quick_exit(0);
    return 0;
}
```

## 输出：

```
Exit Function 2
Exit Function 1
```