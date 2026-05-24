# C++ |静态关键词|问题 6

> 原文:[https://www.geeksforgeeks.org/c-static-keyword-question-6/](https://www.geeksforgeeks.org/c-static-keyword-question-6/)

以下 C++ 程序的输出？

```cpp
#include <iostream>
class Test
{
public:
    void fun();
};
static void Test::fun()   
{
    std::cout<<"fun() is static\n";
}
int main()
{
    Test::fun();   
    return 0;
}
```

由**Pravasi Meet**
**(A)**fun()是静态的
**(B)** 空屏
**(C)** 编译器错误

**答案:****(C)**

**说明:**以上程序编译失败，显示如下错误信息。
【错误】无法声明成员函数“void Test::fun()”具有静态链接[-fpermissive]
在函数“int main()”中:
【错误】无法调用没有对象的成员函数“void Test::fun()”

如果要在类外定义静态函数，那么 static 关键字必须只出现在函数声明中，而不能出现在类外的定义中。

下面的程序现在是正确的。

```cpp
#include <iostream>
class Test
{
public:
    static void fun();
};
void Test::fun()
{
    std::cout<<"fun() is static\n";
}
int main()
{
    Test::fun();
    return 0;
}
```

[本题小考](https://www.geeksforgeeks.org/c-plus-plus-gq/static-keyword-gq/)