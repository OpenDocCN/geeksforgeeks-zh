# c++ 引用成员可以不用声明初始化就可以声明吗？

> 原文:[https://www . geesforgeks . org/can-c-reference-member-be-declaration-not-initialized-with-declaration/](https://www.geeksforgeeks.org/can-c-reference-member-be-declared-without-being-initialized-with-declaration/)

对许多读者来说，这听起来可能是一回事，即

```cpp
class_type *var = NULL;
*var = &some_work;

is same as

class_type *var = &some_work;
```

但实际上，并不是。**当声明和初始化在同一个步骤中完成时，编译器调用复制构造函数，而如果在另一个步骤中完成，编译器调用默认构造函数。**
为了理解这一点，让我们考虑一个例子:
**例子 1:** 当初始化没有在声明的同一步骤完成时

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

class A {
    int& p;

    // Note:basically it is
    // supposed to be an error
    // because this reference
    // member p is not initialized
    // with some variable at the same
    // step of its declaration. But it
    // will run in this case. For us,
    // this is the declaration but
    // not for compiler

public:

    // this line
    // means int &p=w, so p and w
    // both are same. Compiler considers
    // this step as declaration and
    // initialization is done at
    // same step.
    A(int w): p(w)
    {
        cout << p;
    }
};
int main()
{
    A obj(10);
    return 0;
}
```

**输出:**

```cpp
10
```

**示例 2:** 当初始化完成时，声明

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

class A {
    int& p;

public:

    // In this step,
    // compiler will see only
    // declaration not initialization.
    // Therefore this code will
    // give an error.
    A(int w)
    {
        p = w;
        cout << p;
    }
};
int main()
{
    A obj(10);
    return 0;
}
```

**编译错误:**

```cpp
prog.cpp: In constructor 'A::A(int)':
prog.cpp:8:5: error: uninitialized reference member in 'int&' [-fpermissive]
     A(int w)
     ^
prog.cpp:5:10: note: 'int& A::p' should be initialized
     int& p;
          ^
```

**注意:**在这段代码中，一旦创建了一个对象，编译器就会通过运行 a 类的构造函数来给 p 分配内存，现在我们知道引用变量需要在同一个步骤进行初始化，所以会弹出一个叫做“引用成员未初始化”的错误消息。
正如我们在代码 1 中看到的，初始化不是在声明的同一个步骤中完成的，但是我们的代码仍然在运行。但总的来说，规则是“**引用成员应该在同一步**初始化和声明。”
**所以上述问题的答案是肯定和否定的**