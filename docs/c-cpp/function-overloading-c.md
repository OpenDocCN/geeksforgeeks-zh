# c++ 中的函数重载

> 原文:[https://www.geeksforgeeks.org/function-overloading-c/](https://www.geeksforgeeks.org/function-overloading-c/)

函数重载是面向对象编程的一个特征，其中两个或多个函数可以具有相同的名称，但参数不同。

当一个函数名被不同的作业重载时，它被称为函数重载。

在函数重载中，“函数”的名称应该相同，参数应该不同。

函数重载可以看作是 C++ 中多态特性的一个例子。

下面是一个简单的 C++ 例子来演示函数重载。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

void print(int i) {
  cout << " Here is int " << i << endl;
}
void print(double  f) {
  cout << " Here is float " << f << endl;
}
void print(char const *c) {
  cout << " Here is char* " << c << endl;
}

int main() {
  print(10);
  print(10.10);
  print("ten");
  return 0;
}
```

**输出:**

```cpp
Here is int 10 
Here is float 10.1 
Here is char* ten
```

## 函数重载是如何工作的？

*   *完全匹配* :-(函数名和参数)
*   *如果发现* a *不完全匹配:*–

->Char、无符号字符和 short 被提升为 int。

->Float 被提升为 double

*   *如果没有找到匹配*:

->C++ 试图通过标准转换找到匹配。

*   *否则错误🙁*

1.  [功能过载和返回类型](https://www.geeksforgeeks.org/g-fact-75/)
2.  [c++ 中不能重载的函数](https://www.geeksforgeeks.org/function-overloading-in-c/)
3.  [函数重载和 const 关键字](https://www.geeksforgeeks.org/function-overloading-and-const-functions/)
4.  [c++ 中的函数重载与函数覆盖](https://www.geeksforgeeks.org/function-overloading-vs-function-overriding-in-cpp/)

[最近关于 C++ 中函数重载的文章](https://www.geeksforgeeks.org/tag/cpp-overloading/)
如果你发现任何不正确的地方，请写评论，或者你想分享更多关于上面讨论的主题的信息。