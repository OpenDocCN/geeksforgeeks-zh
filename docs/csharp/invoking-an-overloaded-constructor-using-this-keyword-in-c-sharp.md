# 在 C# 中使用这个关键字调用重载的构造函数

> 原文:[https://www . geeksforgeeks . org/调用重载构造函数-使用 c-sharp 中的 this-关键字/](https://www.geeksforgeeks.org/invoking-an-overloaded-constructor-using-this-keyword-in-c-sharp/)

**先决条件:**[**c# 中的构造函数**](https://www.geeksforgeeks.org/c-sharp-constructors/)
C# 提供了一个强大的关键字称为[这个关键字](https://www.geeksforgeeks.org/c-this-keyword/)，这个关键字有很多用法。这里我们使用这个关键字从另一个构造函数调用一个[重载构造函数](https://www.geeksforgeeks.org/c-constructor-overloading/)。
**要点:**

*   当使用此关键字调用构造函数时，该构造函数应该属于同一个类。
*   您也可以在此关键字中传递参数。
*   这个关键字总是指向使用它的同一个类的成员。
*   当您使用此关键字时，它会告诉编译器调用默认构造函数。或者换句话说，它意味着一个不包含参数的构造函数。
    **语法:**

```cs
class X 
{

   public X: this()
   {

      // Code..

   }
}
```

*   *这个*关键字包含的参数类型和数量与调用构造函数中的相同。
    **语法:**

```cs
class X
{
   public X(int x): this(int)
   {

       // Code..
   }
}
```

*   这个概念删除了同一类中属性复制的赋值。

下面的程序说明了如何使用这个关键字调用重载的构造函数:
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate how to invoke
// overloaded constructor using this keyword
using System;
class Geek {

    // Constructor without parameter
    public Geek()
    {
        Console.WriteLine("Hello! Constructor 1");
    }

    // Constructor with parameter
    // Here this keyword is used
    // to call Geek constructor
    public Geek(int a)
    : this()
    {
        Console.WriteLine("Hello! Constructor 2");
    }
}

// Driver Class
public class GFG {

    // Main method
    static public void Main()
    {

        // Create object of Geek class
        Geek obj = new Geek(2);
    }
}
```

**输出:**

```cs
Hello! Constructor 1
Hello! Constructor 2
```

**说明:**在上例中， *Geek* 类包含两个构造函数，即 *Geek()* 不带参数， *Geek(int a)* 带参数。现在我们用 *this()* 关键字在 *Geek(int a)* 中调用 *Geek()* 构造函数。这里 *this()* 关键字不包含任何参数，因为构造函数不包含任何参数。
**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate how to invoke
// overloaded constructor using this keyword
using System;
class Geek {

    // Constructor with parameters
    public Geek(int a, double b, string c)
    {
        Console.WriteLine(a);
        Console.WriteLine(b);
        Console.WriteLine(c);
    }

    // Constructor with parameters
    // Here this keyword is used
    // to call Geek constructor
    public Geek(int a, int b)
        : this(50, 2.9, "Hello")
    {
        Console.WriteLine(a);
        Console.WriteLine(b);
    }
}

// Driver Class
public class GFG {

    // Main method
    static public void Main()
    {

        // Create object of Geek class
        Geek obj = new Geek(15, 30);
    }
}
```

**输出:**

```cs
50
2.9
Hello
15
30
```

**说明:**在上例中， *Geek* 类包含两个构造函数，即 Geek(int a，double b，string c)和 Geek(int a，int b)，两者都是参数化构造函数。现在我们用这个(50，2.9，“Hello”)关键字在 Geek(int a，int b)中调用 Geek(int a，double b，string c)构造函数。这里这个(50，2.9，“Hello”)关键字包含的参数数量和类型与 *Geek(int a，double b，string c)* 构造函数中的相同。