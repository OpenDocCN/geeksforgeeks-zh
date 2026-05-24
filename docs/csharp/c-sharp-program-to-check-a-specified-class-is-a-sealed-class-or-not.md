# 检查指定类是否为密封类的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-check-a-specified-class-is-a-sealed-class-or-not/](https://www.geeksforgeeks.org/c-sharp-program-to-check-a-specified-class-is-a-sealed-class-or-not/)

一个[密封](https://www.geeksforgeeks.org/c-sharp-sealed-class/)类是不会让用户继承该类的类。我们可以使用密封的关键字创建一个密封的类。这个关键字告诉编译器这个类是一个密封类。在本文中，我们将学习如何检查指定的类是否是密封类。所以我们使用类型类的 IsSealed 属性。此属性用于检查给定类型是否密封。

**语法:**

```cs
public bool IsSealed { get; }
```

**Return:** 该属性的返回类型为布尔值。如果给定的类型或类是密封的，它将返回 true，否则，它将返回 false。

**例 1:**

## C#

```cs
// C# program to check if the given 
// class is sealed or not
using System;
using System.Reflection;

// Declare a class without sealed
public class Myclass1
{
    public void display()
    {
        Console.WriteLine("Hello! GeeksforGeeks");
    }
}

// Declare a class with sealed
sealed class Myclass2 
{
    public void Show()
    {
        Console.WriteLine("Hey! GeeksforGeeks");
    }
}

// Driver code
class GFG{

public static void Main(string[] args)
{

    // Check the given class is sealed or not
    // Using IsSealed property
    Console.WriteLine(typeof(Myclass1).IsSealed);
    Console.WriteLine(typeof(Myclass2).IsSealed);
}
}
```

**输出:**

```cs
False
True
```

**例 2:**

## C#

```cs
// C# program to check if the given 
// class is sealed or not
using System;
using System.Reflection;

// Declare a class with sealed keyword
sealed class Myclass 
{
    public void Show()
    {
        Console.WriteLine("Hey! GeeksforGeeks");
    }
}

// Driver code
class GFG{

public static void Main(string[] args)
{

    // Check the given class is sealed or not
    // Using IsSealed property
    if (typeof(Myclass).IsSealed == true)
    {
        Console.WriteLine("The given class is a sealed class");
    }
    else
    {
        Console.WriteLine("The given class is not a sealed class");
    }
}
}
```

**输出:**

```cs
The given class is a sealed class
```