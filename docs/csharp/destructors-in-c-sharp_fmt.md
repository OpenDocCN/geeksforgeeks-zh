# c# 中的析构函数

> 原文:[https://www.geeksforgeeks.org/destructors-in-c-sharp/](https://www.geeksforgeeks.org/destructors-in-c-sharp/)

C# 中的析构函数是类内的方法，用于在不再需要时销毁`类`的实例。析构函数由`隐式调用。NET Framework 的`垃圾收集器，因此程序员无法控制何时调用析构函数。当实例变量或对象不再可达时，它有资格被销毁。

## 要点:

*   `Destructors`是其类独有的，也就是说，一个类不能有多个析构函数。
*   析构函数没有返回类型，并且与类名完全相同（包括大小写）。
*   它与`constructor`不同，因为它的名称前面带有`tilde (~)`。
*   析构函数不接受任何参数和修饰符。
*   不能在结构中定义。它仅用于类。
*   不能重载或继承。
*   在程序退出时调用。
*   在内部，析构函数调用对象基类的`Finalize`方法。

## 语法:

```cs
class Example
{ 
    // Rest of the class
    // members and methods.

// Destructor
   ~Example()
    {
        // Your code
    }

}
```

## 例 1:

```cs
// C# Program to illustrate how 
// a destructor works
using System;

namespace GeeksforGeeks {

class Complex {

// Class members, private 
    // by default
    int real, img;

// Defining the constructor
    public Complex()
    {
        real = 0;
        img = 0;
    }

// SetValue method sets 
    // value of real and img
    public void SetValue(int r, int i)
    {
        real = r;
        img = i;
    }

// DisplayValue displays 
    // values of real and img
    public void DisplayValue()
    {
        Console.WriteLine("Real = " + real);
        Console.WriteLine("Imaginary = " + img);
    }

// Defining the destructor
    // for class Complex
    ~Complex()
    {
        Console.WriteLine("Destructor was called");
    }

} // End class Complex

// Driver Class
class Program {

// Main Method
    static void Main(string[] args)
    {

// Creating an instance of class 
        // Complex C invokes constructor
        Complex C = new Complex();

// Calling SetValue method using
        // instance C Setting values of 
        // real to 2 and img to 3
        C.SetValue(2, 3);

// Displaying values of real
        // and imaginary parts
        C.DisplayValue();

// Instance is no longer needed
        // Destructor will be called

} // End Main

} // End class Program

}
```

## 输出:

```cs
Real = 2
Imaginary = 3
Destructor was called
```