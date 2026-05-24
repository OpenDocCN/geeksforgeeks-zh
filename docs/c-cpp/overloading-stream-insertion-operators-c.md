# 在 C++ 中重载流插入(< >)操作符

> 原文:[https://www . geesforgeks . org/overload-stream-insert-operators-c/](https://www.geeksforgeeks.org/overloading-stream-insertion-operators-c/)

在 C++ 中，流插入运算符“<>”用于输入。
在开始重载这些运算符之前，我们必须了解以下内容。
**1)** cout 是 ostream 类的对象，cin 是 istream 类的对象
**2)** 这些运算符必须作为全局函数重载。如果我们想让他们访问类的私有数据成员，我们必须让他们成为朋友。
**为什么这些操作符一定要重载为全局？**
在运算符重载中，如果一个运算符作为成员重载，那么它一定是该运算符左侧对象的成员。例如，考虑语句“ob1 + ob2”(让 ob1 和 ob2 是两个不同类的对象)。要编译这个语句，我们必须重载“ob1”类中的“+”或者使“+”成为全局函数。
运算符“< <”和“> >”被称为“cout < < ob1”和“cin > > ob1”。所以如果我们想让它们成为成员方法，那么它们必须成为 ostream 和 istream 类的成员，这在大多数情况下不是一个好的选择。因此，这些运算符被重载为具有两个参数的全局函数，cout 和用户定义类的对象。
下面是一个完整的 C++ 程序，演示< >运算符的重载。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

class Complex
{
private:
    int real, imag;
public:
    Complex(int r = 0, int i =0)
    {  real = r;   imag = i; }
    friend ostream & operator << (ostream &out, const Complex &c);
    friend istream & operator >> (istream &in,  Complex &c);
};

ostream & operator << (ostream &out, const Complex &c)
{
    out << c.real;
    out << "+i" << c.imag << endl;
    return out;
}

istream & operator >> (istream &in,  Complex &c)
{
    cout << "Enter Real Part ";
    in >> c.real;
    cout << "Enter Imaginary Part ";
    in >> c.imag;
    return in;
}

int main()
{
   Complex c1;
   cin >> c1;
   cout << "The complex object is ";
   cout << c1;
   return 0;
}
```

输出:

```cpp
Enter Real Part 10
Enter Imaginary Part 20
The complex object is 10+i20
```

如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息