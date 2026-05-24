# C++ |异常处理|问题 4

> 原文:[https://www . geesforgeks . org/c-异常处理-问题-4/](https://www.geeksforgeeks.org/c-exception-handling-question-4/)

以下程序的输出

```cpp
#include<iostream>
using namespace std;

class Base {};
class Derived: public Base {};
int main()
{
   Derived d;
   try {
       throw d;
   }
   catch(Base b) {
        cout<<"Caught Base Exception";
   }
   catch(Derived d) {
        cout<<"Caught Derived Exception";
   }
   return 0;
}
```

**(A)** 捕获到派生异常
**(B)** 捕获到基异常
**(C)** 编译器错误

**答案:****(B)**

**解释:**如果基类和派生类都被捕获为异常，那么派生类的 catch 块必须出现在基类之前。如果我们把基类放在第一位，那么派生类 catch 块将永远不会到达。

在 Java 中，编译器本身不允许在派生之前捕获基类异常。在 C++ 中，编译器可能会给出警告，但会编译代码。

[本题竞猜](https://www.geeksforgeeks.org/quiz-corner-gq/)