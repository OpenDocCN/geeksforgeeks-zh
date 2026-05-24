# c++ 中的函数重载与函数覆盖

> 原文:[https://www . geesforgeks . org/function-overriding-override-in-CPP/](https://www.geeksforgeeks.org/function-overloading-vs-function-overriding-in-cpp/)

[**函数重载**](https://www.geeksforgeeks.org/function-overloading-c/) **(编译时实现)**

它通过改变签名提供了函数的多种定义，即改变参数的数量，改变参数的数据类型，返回类型不起任何作用。

*   它可以在基类和派生类中完成。
*   **例:**

```cpp
void area(int a);
void area(int a, int b); 
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Function Overloading
#include <iostream>
using namespace std;

// overloaded functions
void test(int);
void test(float);
void test(int, float);

int main()
{
    int a = 5;
    float b = 5.5;

    // Overloaded functions
    // with different type and
    // number of parameters
    test(a);
    test(b);
    test(a, b);

    return 0;
}

// Method 1
void test(int var)
{
    cout << "Integer number: " << var << endl;
}

// Method 2
void test(float var)
{
    cout << "Float number: "<< var << endl;
}

// Method 3
void test(int var1, float var2)
{
    cout << "Integer number: " << var1;
    cout << " and float number:" << var2;
}
```

输出:

```cpp
Integer number: 5
Float number: 5.5
Integer number: 5 and float number: 5.5
```

**函数覆盖(在运行时实现)**
它是基类函数在其派生类中的重新定义，具有相同的签名，即返回类型和参数。

*   只能在派生类中完成。
*   **示例:**

```cpp
Class a
{
public: 
      virtual void display(){ cout << "hello"; }
};

Class b:public a
{
public: 
       void display(){ cout << "bye";}
};
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// CPP program to illustrate
// Function Overriding
#include<iostream>
using namespace std;

class BaseClass
{
public:
    virtual void Display()
    {
        cout << "\nThis is Display() method"
                " of BaseClass";
    }
    void Show()
    {
        cout << "\nThis is Show() method "
               "of BaseClass";
    }
};

class DerivedClass : public BaseClass
{
public:
    // Overriding method - new working of
    // base class's display method
    void Display()
    {
        cout << "\nThis is Display() method"
               " of DerivedClass";
    }
};

// Driver code
int main()
{
    DerivedClass dr;
    BaseClass &bs = dr;
    bs.Display();
    dr.Show();
}
```

输出:

```cpp
This is Display() method of DerivedClass
This is Show() method of BaseClass
```

**功能过载 VS 功能超驰:**

1.  **继承:**当一个类从另一个类继承时，函数被覆盖。没有继承就可能发生重载。
2.  **函数签名:**重载函数的函数签名必须不同，即参数数量或参数类型应该不同。在重写时，函数签名必须相同。
3.  **功能范围:**被覆盖的功能在不同的范围内；而重载函数在相同的范围内。
4.  **函数的行为:**当派生类函数必须做一些与基类函数不同的工作时，需要重写。重载用于具有相同名称的函数，这些函数的行为取决于传递给它们的参数。

本文由**马扎米克****雅什辛格拉**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。