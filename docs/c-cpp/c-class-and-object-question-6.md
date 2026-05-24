# C++ |类和对象|问题 6

> 原文:[https://www . geesforgeks . org/c-class-and-object-question-6/](https://www.geeksforgeeks.org/c-class-and-object-question-6/)

关于以下程序，以下哪一项是正确的

```cpp
#include <iostream>
class Test
{
public:
    int i;
    void get();
};
void Test::get()
{
    std::cout << "Enter the value of i: ";
    std::cin >> i;
}
Test t;  // Global object
int main()
{
    Test t;  // local object
    t.get();
    std::cout << "value of i in local t: "<<t.i<<'\n';
    ::t.get(); 
    std::cout << "value of i in global t: "<<::t.i<<'\n';
    return 0;
}
```

由**Pravasi Meet**
**(A)**编译器错误:不能有两个类名相同的对象
**(B)** 第“::t.get()”行编译器错误

**(C)** 编译运行良好

**回答:** **(C)**

**说明:**以上程序编译运行良好&。像变量一样，可以在不同的范围内创建两个同名的对象&。

[本题小考](https://www.geeksforgeeks.org/c-plus-plus-gq/class-and-object-gq/)