# c++ 程序输出|第 10 集

> 原文:[https://www.geeksforgeeks.org/output-of-c-program-set-10-2/](https://www.geeksforgeeks.org/output-of-c-program-set-10-2/)

预测以下 C++ 程序的输出。
**问题 1**

## C

```cpp
#include<iostream>
#include<string.h>
using namespace std;

class String
{
    char *p;
    int len;
public:
    String(const char *a);
};

String::String(const char *a)
{
    int length = strlen(a);
    p = new char[length +1];
    strcpy(p, a);
    cout << "Constructor Called " << endl;
}

int main()
{
    String s1("Geeks");
    const char *name = "forGeeks";
    s1 = name;
    return 0;
}
```

输出:

```cpp
Constructor called
Constructor called
```

输出的第一行由语句“字符串 s1(“极客”)打印第二行由语句“s1 = name”打印。第二次调用的原因是，单个参数构造函数也作为转换运算符工作(详见[本](https://www.geeksforgeeks.org/g-fact-35/)和[本](https://www.geeksforgeeks.org/g-fact-93/))。
**问题 2**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include<iostream>

using namespace std;

class A
{
    public:
    virtual void fun() {cout << "A" << endl ;}
};
class B: public A
{
    public:
    virtual void fun() {cout << "B" << endl;}
};
class C: public B
{
    public:
    virtual void fun() {cout << "C" << endl;}
};

int main()
{
    A *a = new C;
    A *b = new B;
    a->fun();
    b->fun();
    return 0;
}
```

输出:

```cpp
C
B
```

基类指针可以指向子类的对象。基类指针也可以指向子类的对象。因此，行“A *a =新 C；”是有效的。行“a-> fun()；”打印“C”，因为指向的对象属于 C 类，并且 fun()在 A 和 B 中都被声明为虚拟的(详见[本](http://en.wikipedia.org/wiki/Virtual_function))。第二行输出由语句“b- > fun()”打印。
如果您发现任何答案/解释不正确，或者想分享更多关于上述主题的信息，请写评论。