# C# |显式接口实现

> 原文:[https://www . geesforgeks . org/c-sharp-explicit-interface-implementation/](https://www.geeksforgeeks.org/c-sharp-explicit-interface-implementation/)

一个 [**界面**](https://www.geeksforgeeks.org/c-sharp-interface/) 是一个松散绑定的项目的集合，这些项目具有共同的功能或属性。接口包含方法签名、属性、事件等。使用接口是为了让一个类或结构可以实现多个行为。C# 不支持 [**多重继承**](https://www.geeksforgeeks.org/c-sharp-multiple-inheritance-using-interfaces/) 的概念，因为它会引起歧义。但是很多现实生活中的对象继承的属性不仅仅是一种类型，因此使用接口来代替扩展类。

接口只由签名组成，而不是它的实现，因此，实现它的任何类或结构都必须通过重写来提供实现。

#### 什么是显式接口实现，何时使用？

显式地告诉编译器某个特定成员属于该特定接口称为显式接口实现。
如果一个类从多个具有相同签名的方法的接口实现，那么对这样一个方法的调用将实现相同的方法，而不是接口特定的方法。这将破坏使用不同接口的全部目的。这就是显式实现出现的时候。使用显式实现，您可以告诉编译器您正在重载哪个接口的方法，并且可以为不同接口的方法提供不同的功能。任何其他类型的成员(如属性、事件)也是如此。

**语法:**

```cs
class ClassName : InterfaceName
{
    returnType InterfaceName.method()
    { 
          // Your Code 
    }
}
```

**示例 1:** 这个程序展示了显式接口实现的使用。这里我们有两个接口 *I1* 和 I2，它们具有相同的名为 printMethod 的方法签名，返回类型为 void。类 *C* 实现了这两个接口，因此我们使用显式接口实现来区分方法。

## C#

```cs
// C# Program to show the use of
// Explicit interface implementation
using System;

interface I1 {

    void printMethod();
}

interface I2 {

    void printMethod();
}

// class C implements two interfaces
class C : I1, I2 {

    // Explicitly implements method of I1
    void I1.printMethod()
    {
        Console.WriteLine("I1 printMethod");
    }

    // Explicitly implements method of I2
    void I2.printMethod()
    {
        Console.WriteLine("I2 printMethod");
    }
}

// Driver Class
class GFG {

    // Main Method
    static void Main(string[] args)
    {
        I1 i1 = new C();
        I2 i2 = new C();

        // call to method of I1
        i1.printMethod();

        // call to method of I2
        i2.printMethod();
    }
}
```

**Output:** 

```cs
I1 printMethod
I2 printMethod
```

**示例 2:** 这里，我们有一个界面金字塔，方法是*绘制金字塔*。类*显示*继承了这个方法，并提供了一个在屏幕上打印“ *** ”金字塔的实现。我们使用显式实现来覆盖 draw 金字塔方法。

## C#

```cs
// C# Program to show the use of
// Explicit interface implementation
using System;

interface Pyramid {

    // Method signature
    void drawPyramid();
}

// Implements Pyramid
class Display : Pyramid {

    // Using Explicit implementation
    void Pyramid.drawPyramid()
    {
        for (int i = 1; i <= 10; i++)
        {
            for (int k = i; k < 10; k++)
                Console.Write(" ");

            for (int j = 1; j <= (2 * i - 1); j++)
                Console.Write("*");

            Console.WriteLine();
        }
    }
}

// Driver Code
class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Create object of the class using Interface
        Pyramid obj = new Display();

        // call method
        obj.drawPyramid();
    }
}
```

**Output:** 

```cs
         *
        ***
       *****
      *******
     *********
    ***********
   *************
  ***************
 *****************
*******************
```

**示例 3:** 我们可以对偶数属性和接口的基本上任何其他成员使用显式接口实现。这里我们在界面 *I1* 和 *I2* 中分别有属性 *X* 和方法 *X* ，名称相同，返回类型相同。我们只在方法 *X* 上使用显式接口实现。这样，编译器将使用属性 *X* ，除非另有说明。

## C#

```cs
// C# Program to show the use of
// Explicit interface implementation
using System;

interface I1 {

    // Property X
    int X
    {
        set;
        get;
    }
}

interface I2 {

    // Method X
    int X();
}

class C : I1, I2 {

    int x;

    // Implicit implementation of
    // the property
    public int X
    {
        set { x = value; }
        get { return x; }
    }

    // Explicit implementation of
    // the method
    int I2.X()
    {
        return 0;
    }
}

// Driver Code
class GFG {

    // Main Method
    static void Main(string[] args)
    {
        C c = new C();
        I2 i2 = new C();

        // Invokes set accessor
        c.X = 10;

        // Invokes get accessor
        Console.WriteLine("Value of x set using X"+
                             " from I1 is " + c.X);

        // Call to the X method
        Console.WriteLine("Value returned by I2.X()"+
                                    " is " + i2.X());
    }
}
```

**Output:** 

```cs
Value of x set using X from I1 is 10
Value returned by I2.X() is 0
```