# C# |构造函数中的继承

> 原文:[https://www . geeksforgeeks . org/c-sharp-继承在构造函数中/](https://www.geeksforgeeks.org/c-sharp-inheritance-in-constructors/)

在 C# 中，基类和派生类都可以有自己的构造函数。用于实例化基类对象的基类构造函数和用于实例化派生类对象的派生类构造函数。在继承中，派生类继承基类的所有成员(字段、方法)，但是**派生类不能继承基类的构造函数**，因为构造函数不是类的成员。不允许派生类继承构造函数，只允许调用基类的构造函数。

在 C# 中，当我们在继承中使用**构造函数时，会出现两种不同的情况**，如下所示:

**情况 1:** 在这种情况下，**只有派生类包含构造函数**。因此，派生类的对象由该构造函数实例化，基类的对象由默认构造函数自动实例化。

**例:**

```cs
// C# program to illustrate the
// concept of inheritance in the
// constructor when the derived
// class contains a constructor
using System;

// Class Tank to give the
// dimension of the tank
class Tank {

    double t_radius;
    double t_height;

    // Properties for Radius and Height
    public double Radius
    {
        get { 
               return t_radius; 
            }

        set {
               t_radius = value < 0 ? -value : value;
            }
    }

    public double Height
    {
        get { 
               return t_height; 
            }

        set { 
              t_height = value < 0 ? -value : value; 
            }
    }

    // Display the dimension of tanks
    public void DisplayDimension()
    {
        Console.WriteLine("The radius of tank is :" + Radius 
                 + " and the height of tank is :" + Height);
    }
}

// A derived class AreaOfTank 
// inheriting Tank Class
class AreaOfTank : Tank {

    string Color;

    // Constructor
    public AreaOfTank(string c, double r, double h)
    {

        // from base class
        Radius = r;
        Height = h;

        // from derived class
        Color = c;
    }

    // Return area of tank
    public double Area()
    {
        return 2 * 3.14 * Radius * Height;
    }

    // Display the color of tank
    public void DisplayColor()
    {
        Console.WriteLine("The Color of tank is " 
                                        + Color);
    }
}

// Driver Class
class GFG {

    // Main Method
    static void Main()
    {

        // Create and initialize the
        // object of AreaOfTank
        AreaOfTank t1 = new AreaOfTank("Green", 6.0, 12.0);
        t1.DisplayColor();
        t1.DisplayDimension();
        Console.WriteLine("Area is " + t1.Area());
    }
}
```

**输出:**

```cs
The Color of tank is Green
The radius of tank is :6 and the height of tank is :12
Area is 452.16

```