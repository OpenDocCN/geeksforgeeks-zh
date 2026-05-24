# C++ |虚函数|第 14 题

> 原文:[https://www . geesforgeks . org/c-virtual-functions-question-8/](https://www.geeksforgeeks.org/c-virtual-functions-question-8/)

构造函数可以是虚拟的吗？

下面的程序会编译吗？

```cpp
#include <iostream>
using namespace std;
class Base {
public:
  virtual Base() {}   
};
int main() {
   return 0;
}
```

**(A)** 是
**(B)** 否

**回答:** **(B)**

**说明:**没有什么比得上虚拟构造器。将构造函数虚拟化没有意义，因为构造函数负责创建一个对象，并且不能通过虚拟关键字的方式委托给任何其他对象。

[本题小考](https://www.geeksforgeeks.org/c-plus-plus-gq/virtual-functions-gq/)