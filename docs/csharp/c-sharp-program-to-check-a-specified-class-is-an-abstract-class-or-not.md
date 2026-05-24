# 检查指定类是否为抽象类的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-check-a-specific-class-is-abstract-class-or-not/](https://www.geeksforgeeks.org/c-sharp-program-to-check-a-specified-class-is-an-abstract-class-or-not/)

[抽象](https://www.geeksforgeeks.org/c-sharp-abstraction/)是隐藏内部细节，只显示功能的过程。抽象关键字用在类或方法之前，将类或方法声明为抽象的。在本文中，我们将学习如何检查指定的类是否是抽象类。为了完成这个任务，我们使用类型类的**属性。此属性用于检查给定的类型(即类名)是否是抽象的，是否必须被重写。如果指定的类型(即类名)是抽象的，它将返回 true。否则，返回 false。**

**语法**:

```cs
public bool IsAbstract { get; }
```

**例 1:**

## C#

```cs
// C# program to check a specified class is
// an abstract class or not
using System;
using System.Reflection;

// Declare an abstract class named Geeks
abstract class Geeks 
{

    // Abstract method
    public abstract void geeksmethod();
}

class GFG{

static void Main()
{

    // Get the type of class by using typeof() function
    // Check the class is abstract or not by using
    // IsAbstract property
    if (typeof(Geeks).IsAbstract == true) 
    {
        Console.WriteLine("This is abstract");
    }
    else 
    {
        Console.WriteLine("This is not abstract");
    }
}
}
```

**输出:**

```cs
This is abstract
```

**例 2:**

## C#

```cs
// C# program to check a specified class is
// an abstract class or not
using System;
using System.Reflection;

// Declare an abstract class named Geeks
abstract class Geeks1 
{

    // Abstract method
    public abstract void geeksmethod();
}

// Declare a class named Geeks2
class Geeks2
{

    // Method 
    public void gfgfunc()
    {
        Console.WriteLine("This is method");
    }
}

// Declare a class named Geeks3
// It implement abstract class
class Geeks3:Geeks1 
{ 

    // Method 
    public override void geeksmethod()
    {
        Console.WriteLine("This is method");
    }
}

class GFG{

// Driver code
static void Main()
{

    // Get the type of class by using typeof() function
    // Check the class is abstract or not by using
    // IsAbstract property
    bool res1 = typeof(Geeks1).IsAbstract;
    bool res2 = typeof(Geeks2).IsAbstract;
    bool res3 = typeof(Geeks3).IsAbstract;

    Console.WriteLine("Is Geeks1 class is abstract class?" + res1);
    Console.WriteLine("Is Geeks2 class is abstract class?" + res2);
    Console.WriteLine("Is Geeks3 class is abstract class?" + res3);
}
}
```

**输出:**

```cs
Is Geeks1 class is abstract class?True
Is Geeks2 class is abstract class?False
Is Geeks3 class is abstract class?False
```