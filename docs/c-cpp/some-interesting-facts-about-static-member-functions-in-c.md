# 关于 C++ 中静态成员函数的一些有趣事实

> 原文:[https://www . geesforgeks . org/some-interest-facts-about-static-member-functions-in-c/](https://www.geeksforgeeks.org/some-interesting-facts-about-static-member-functions-in-c/)

**1)** 静态成员函数没有[这个指针](https://www.geeksforgeeks.org/this-pointer-in-c/)。
例如，以下程序编译失败，错误为*“`这'不适用于静态成员函数”*

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
class Test {     
   static Test * fun() {
     return this; // compiler error
   }
};

int main()
{
   getchar();
   return 0;
}
```

**2)** 静态成员函数不能是虚的(参见[本](https://www.geeksforgeeks.org/g-fact-29/) G-Fact)
**3)** 同名成员函数声明和名称参数-类型-列表不能重载，如果其中任何一个是静态成员函数声明。
例如，以下程序编译失败，错误为“*‘void Test::fun()’和‘static void Test::fun()’不能重载*

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
class Test {
   static void fun() {}
   void fun() {} // compiler error
};

int main()
{
   getchar();
   return 0;
}
```

**4)** 静态成员函数不能声明为 *const* 、 *volatile* 或 *const volatile* 。
例如，以下程序编译失败，出现错误*“静态成员函数‘static void Test::fun()’不能有‘const’方法限定符”*

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
class Test {     
   static void fun() const { // compiler error
     return;
   }
};

int main()
{
   getchar();
   return 0;
}
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
参考文献:
T2