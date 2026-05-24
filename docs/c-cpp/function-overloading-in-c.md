# c++ 中不能重载的函数

> 原文:[https://www.geeksforgeeks.org/function-overloading-in-c/](https://www.geeksforgeeks.org/function-overloading-in-c/)

在 C++ 中，下列函数声明**不能**重载。

1)仅在返回类型上不同的函数声明。例如，以下程序编译失败。

```cpp
#include<iostream>
int foo() { 
  return 10; 
}

char foo() { 
  return 'a'; 
}

int main()
{
   char x = foo();
   getchar();
   return 0;
}
```

2)具有相同名称和名称参数类型列表的成员函数声明，如果其中任何一个是静态成员函数声明，则不能重载。例如，以下程序编译失败。

```cpp
#include<iostream>
class Test {
   static void fun(int i) {}
   void fun(int i) {}   
};

int main()
{
   Test t;
   getchar();
   return 0;
}
```

3)仅指针*与数组[]不同的参数声明是等效的。也就是说，数组声明被调整为指针声明。在参数类型中，只有第二个和后续的数组维度是重要的。例如，以下两个函数声明是等价的。

```cpp
int fun(int *ptr);
int fun(int ptr[]); // redeclaration of fun(int *ptr)
```

4)参数声明的不同之处仅在于一个是函数类型，另一个是指向相同函数类型的指针，它们是等价的。

```cpp
void h(int ());
void h(int (*)()); // redeclaration of h(int())
```

5)仅在常量和/或变量存在或不存在时不同的参数声明是等效的。也就是说，在确定声明、定义或调用哪个函数时，忽略每个参数类型的常量和易失性类型说明符。例如，以下程序编译失败，错误为*“重新定义‘int f(int)’”*

示例:

```cpp
#include<iostream>
#include<stdio.h>

using namespace std;

int f ( int x) {
    return x+10;
}

int f ( const int x) {
    return x+10;
}

int main() {     
  getchar();
  return 0;
}
```

只有在参数类型规范最外层的 const 和 volatile 类型说明符以这种方式被忽略；隐藏在参数类型规范中的 const 和 volatile 类型说明符非常重要，可以用来区分重载函数声明。具体来说，对于任何类型的 T，
“指向 T 的指针”、“指向 const 的指针”和“指向 volatile T 的指针”被认为是不同的参数类型，就像“对 T 的引用”、“对 const 的引用”和“对 volatile T 的引用”一样。例如，参见文基发布的[这篇评论](https://www.geeksforgeeks.org/archives/9707/comment-page-1#comment-3319)中的例子。

6)只有默认参数不同的两个参数声明是等价的。例如，以下程序编译失败，错误为*“重新定义‘int f(int，int)’”*

```cpp
#include<iostream>
#include<stdio.h>

using namespace std;

int f ( int x, int y) {
    return x+10;
}

int f ( int x, int y = 10) {
    return x+y;
}

int main() {     
  getchar();
  return 0;
}
```

参考文献:
[http://www . open-STD . org/JTC 1/sc22/wg21/docs/papers/2005/n 1905 . pdf](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2005/n1905.pdf)

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。