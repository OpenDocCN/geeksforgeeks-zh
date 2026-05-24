# C # 8.0 中的静态本地功能

> 原文:[https://www . geesforgeks . org/static-local-function-in-c-sharp-8-0/](https://www.geeksforgeeks.org/static-local-function-in-c-sharp-8-0/)

在 C# 7.0 中，引入了局部函数。局部函数允许您在已经定义的方法体内声明一个方法。或者换句话说，我们可以说局部函数是一个函数的私有函数，它的作用域仅限于创建它的那个函数。局部函数的类型与定义它的函数的类型相似。您只能从它们的容器成员中调用本地函数。

**例:**

## c#

```cs
// Simple C# program to
// illustrate local function
using System;

class Program {

    // Main method
    public static void Main()
    {
        // Here SubValue is the local
        // function of the main function
        void SubValue(int a, int b)
        {
            Console.WriteLine("Value of a is: " + a);
            Console.WriteLine("Value of b is: " + b);
            Console.WriteLine("final result: {0}", a - b);
            Console.WriteLine();
        }

        // Calling Local function
        SubValue(30, 10);
        SubValue(80, 60);
    }
}
```

**输出:**

```cs
Value of a is: 30
Value of b is: 10
final result: 20

Value of a is: 80
Value of b is: 60
final result: 20
```

但是在 C# 7.0 中，不允许在局部函数中使用静态修饰符，或者换句话说，不允许创建静态局部函数。这个特性是在 C# 8.0 中添加的。在 C# 8.0 中，您可以在局部函数中使用静态修饰符。这确保了静态局部函数不会引用封闭或周围范围内的任何变量。如果静态局部函数试图从封闭范围访问变量，那么编译器将抛出一个错误。让我们借助给定的例子来讨论这个概念:

**例 1:**

## C#

```cs
// Simple C# program to illustrate
// the static local function
using System;

class Program {

    // Main method
    public static void Main()
    {
        // Here AreaofCircle is the local
        // function of the main function
        void AreaofCircle(double a)
        {
            double ar;
            Console.WriteLine("Radius of the circle: " + a);

            ar = 3.14 * a * a;

            Console.WriteLine("Area of circle: " + ar);

            // Calling static local function
            circumference(a);

            // Circumference is the Static local function
            static void circumference(double radii)
            {
                double cr;
                cr = 2 * 3.14 * radii;
                Console.WriteLine("Circumference of the circle is: " + cr);
            }
        }

        // Calling function
        AreaofCircle(30);
    }
}
```

**输出:**

```cs
Radius of the circle: 30
Area of circle: 2826
Circumference of the circle is: 188.4
```

**例 2:**

## c#

```cs
// Simple C# program to illustrate
// the static local function
using System;

class Program {

    // Main method
    public static void Main()
    {
        // Here AreaofCircle is the local
        // the function of the main function
        void AreaofCircle(double a)
        {
            double ar;
            Console.WriteLine("Radius of the circle: " + a);

            ar = 3.14 * a * a;

            Console.WriteLine("Area of circle: " + ar);

            // Circumference is the Static local function
            // If circumference() try to access the enclosing
            // scope variable, then the compile will give error
            static void circumference()
            {
                double cr;
                cr = 2 * 3.14 * a;
                Console.WriteLine("Circumference of the circle is: " + cr);
            }
        }

        // Calling function
        AreaofCircle(30);
    }
}
```

**输出:**

```cs
Error CS8421: A static local function cannot contain a reference to 'a'. (CS8421) (f)
```