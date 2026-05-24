# “删除此”在 C++ 中

> 原文:[https://www.geeksforgeeks.org/delete-this-in-c/](https://www.geeksforgeeks.org/delete-this-in-c/)

理想情况下*删除*操作符不应用于*这个*指针。但是，如果使用，则必须考虑以下几点。
1) *删除*操作符只对使用操作符*新*分配的对象起作用(见[本帖](https://www.geeksforgeeks.org/g-fact-30/))。如果对象是用 new 创建的，那么我们可以做*删除这个*，否则行为未定义。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
class A
{
  public:
    void fun()
    {
        delete this;
    }
};

int main()
{
  /* Following is Valid */
  A *ptr = new A;
  ptr->fun();
  ptr = NULL; // make ptr NULL to make sure that things are not accessed using ptr.

  /* And following is Invalid: Undefined Behavior */
  A a;
  a.fun();

  getchar();
  return 0;
}
```

2)一旦*删除此*完成，删除后被删除对象的任何成员都不应被访问。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>
using namespace std;

class A
{
  int x;
  public:
    A() { x = 0;}
    void fun() {
      delete this;

      /* Invalid: Undefined Behavior */
      cout<<x; // this is working
    }
};

int main()
{
  A* obj = new A;
  obj->fun();
  return 0;
}
```

**Output**

```cpp
0
```

**最好的办法就是完全不做** ***删除这个*** **。**
感谢蛇湖提供以上详情。
参考文献:
[https://www . securecoding . cert . org/converge/display/cplusplus/OOP 05-CPP。+避免+删除+本](https://www.securecoding.cert.org/confluence/display/cplusplus/OOP05-CPP.+Avoid+deleting+this)
[http://en.wikipedia.org/wiki/This_%28computer_science%29](http://en.wikipedia.org/wiki/This_%28computer_science%29)
本文由**拉胡尔·古普塔**供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。