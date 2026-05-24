# 我们自己写的时候，C++ 编译器会创建默认构造函数吗？

> 原文:[https://www . geesforgeks . org/does-c-编译器-创建-默认-构造函数-当我们-编写-我们自己的/](https://www.geeksforgeeks.org/does-c-compiler-create-default-constructor-when-we-write-our-own/)

在 C++ 中，编译器默认为每个类创建默认构造函数。但是，如果我们定义自己的构造函数，编译器不会创建默认的构造函数。这是因为默认构造函数不接受任何参数，如果创建了两个默认构造函数，编译器很难知道应该调用哪个默认构造函数。

例如，程序 1 编译没有任何错误，但程序 2 编译失败，错误为“调用‘myInteger::myInteger()’没有匹配的函数”
**程序 1**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>

using namespace std;

class myInteger
{
   private:
     int value;

     //...other things in class 
};

int main()
{
  myInteger I1;
  getchar();
  return 0;
}
```

**程序 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>

using namespace std;

class myInteger
{
   private:
     int value;
   public:
     myInteger(int v)  // parameterized constructor
     {  value = v;  }

     //...other things in class 
};

int main()
{
  myInteger I1;
  getchar();
  return 0;
}
```

如果你在上面的 GFact 中发现任何不正确的地方，或者你想分享更多关于上面讨论的主题的信息，请写评论。
参考文献:
[http://en.wikipedia.org/wiki/Default_constructor](http://en.wikipedia.org/wiki/Default_constructor)
T5】http://publib . boulder . IBM . com/info center/lnx comp/v8v 101/index . JSP？topic =/com . IBM . xlcpp8l . doc/language/ref/cplr 375 . htm