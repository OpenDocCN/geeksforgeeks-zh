# c# 中的析构函数

> 原文:[https://www.geeksforgeeks.org/destructors-in-c-sharp/](https://www.geeksforgeeks.org/destructors-in-c-sharp/)

C# 中的析构函数是类内的方法，用于在不再需要时销毁[类](https://www.geeksforgeeks.org/c-class-and-object/)的实例。析构函数由[隐式调用。NET Framework 的](https://www.geeksforgeeks.org/introduction-to-net-framework/)垃圾收集器，因此程序员无法控制何时调用析构函数。当实例变量或对象不再可达时，它有资格被销毁。

**要点:**

*   Destructors are unique to their classes, that is, a class cannot have more than one destructor.
*   The destructor has no return type and is exactly the same as the class name (including the same case).
*   It is different from [constructor](https://www.geeksforgeeks.org/c-sharp-constructors/) because its name is preceded by *tilde (~)* .
*   The destructor does not accept any parameters and modifiers.
*   Cannot be defined in a structure. It is only used for classes.
*   Cannot overload or inherit.
*   Called when the program exits.
*   Internally, the destructor calls the Finalize method of the object base class.

**语法:**

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

**例 1:**

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

**输出:**

```cs
Real = 2
Imaginary = 3
Destructor was called

```