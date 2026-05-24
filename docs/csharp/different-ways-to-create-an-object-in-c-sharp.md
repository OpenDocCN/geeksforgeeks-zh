# 在 C# 中创建对象的不同方式

> 原文:[https://www . geeksforgeeks . org/用不同的方法创建 c-sharp 中的对象/](https://www.geeksforgeeks.org/different-ways-to-create-an-object-in-c-sharp/)

完全面向对象的语言意味着一切都被表示为对象，但是不能区分基元类型和类的对象，但是 C# 不是纯粹面向对象的，因为它在一定程度上支持许多过程性编程概念，比如指针。对象是面向对象编程的基本单元，代表现实生活中的实体。一个典型的 C# 程序创建许多对象，正如你所知道的，这些对象通过调用方法进行交互。我们可以通过以下方式在 C# 中创建对象:
**1)使用‘new’运算符:**类是引用类型，在运行时，引用类型的任何对象都被赋予空值，除非它是使用新运算符声明的。新运算符仅在运行时将内存中的空间分配给对象，这意味着分配是动态的。
**语法:**

```cs
// The className() is a call
// to the constructor
className ObjectName = new className();   
```

**注意:**[构造函数](https://www.geeksforgeeks.org/c-sharp-constructors/)可以是默认构造函数，也可以是自定义构造函数。
**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# Program to show the use
// of the new Operator
using System;

namespace NewOperator {

class Rectangle {

    public int length, breadth;

    // Parameterized Constructor
    // User defined
    public Rectangle(int l, int b)
    {
        length = l;
        breadth = b;
    }

    // Method to Calculate Area
    // of the rectangle
    public int Area()
    {
        return length * breadth;
    }
}

// Driver Class
class Program {

    // Main Method
    static void Main(string[] args)
    {
        // Creating an object using 'new'
        // Calling the parameterized constructor
        // With parameters 10 and 12
        Rectangle rect1 = new Rectangle(10, 12);

        // To display are of the Rectangle
        int area = rect1.Area();
        Console.WriteLine("The area of the"+
                   " Rectangle is " + area);
    }
}
}
```

**Output:** 

```cs
The area of the Rectangle is 120
```

**2)创建对现有对象的引用:**引用只能用类名和引用名声明。引用不能独立存在。它必须被分配给同一个类的一个已经存在的对象。引用中所做的任何更改都将保存到它所引用的对象中。有点像化名。
**语法:**

```cs
className RefName;
RefName = objectName;
```

**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# Program to show the use
// of references
using System;

namespace Reference {

class Triangle {

    public int side, altitude;
    // Not defining a constructor

    // Method to calculate area
    // of the Triangle
    public double Area()
    {
        return (double)0.5 * side * altitude;
    }
}

// Driver Class
class Program {

    // Main Method
    static void Main(string[] args)
    {
        // Creating an object using new
        // calls the default constructor
        Triangle tri1 = new Triangle();

        // Only creates a reference of
        // type Triangle
        Triangle tri2;

        // Displaying area of tri1
        Console.WriteLine("Area of tri1 is "
                             + tri1.Area());

        // Assigns the reference to tri1
        tri2 = tri1;

        // Making changes in tri2
        tri2.side = 5;
        tri2.altitude = 7;

        // Displaying area of tri1
        // Changes made in the reference tri2
        // are reflected in tri1 also
        Console.WriteLine("Area of tri1 is "
                             + tri1.Area());
    }
}
}
```

**Output:** 

```cs
Area of tri1 is 0
Area of tri1 is 17.5
```

**3)创建对象数组:**如果需要多个相同类别的对象，可以创建一个对象数组。这将要求您首先声明数组，然后初始化每个元素{在这种情况下是对象}。您可以使用 for 循环进行初始化。
**语法:**

```cs
className[] arrayName = new className[size];
```

## c sharp . c sharp . c sharp . c sharp

```cs
// C# Program to illustrate how to
// create the array of objects
using System;

namespace ArrayofObjects {

class Circle {

    public int radius;

    // Defining Constructor
    public Circle()
    {
        radius = 0;
    }

    // Method to set value of radius
    public void setValue(int r)
    {
        radius = r;
    }

    // Method to calculate the
    // area of the Circle
    public double Area()
    {
        return (double)3.14 * radius * radius;
    }
}

// Driver Class
class Program {

    // Main Method
    static void Main(string[] args)
    {
        // To declare an array of two objects
        Circle[] circleArray = new Circle[2];

        // Initialize the objects
        circleArray[0] = new Circle();
        circleArray[1] = new Circle();

        // to set values for the radius
        circleArray[0].setValue(1);
        circleArray[1].setValue(2);

        // for loop to display areas
        for (int i = 0; i < circleArray.Length; i++)
        {
            Console.Write("Area of circle with radius " + (i + 1));
            Console.Write(" is " + circleArray[i].Area() + "\n");
        }
    }
}
}
```

**Output:** 

```cs
Area of circle with radius 1 is 3.14
Area of circle with radius 2 is 12.56
```