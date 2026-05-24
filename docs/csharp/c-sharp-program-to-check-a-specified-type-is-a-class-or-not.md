# 检查指定类型是否为类的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-check-a-specified-type-is-a-class-or-not/](https://www.geeksforgeeks.org/c-sharp-program-to-check-a-specified-type-is-a-class-or-not/)

类是方法、变量和对象的集合。或者我们可以说，类是一个蓝图，使用它来创建一个对象。因此，为了检查指定的类型是否是类以及委托，我们使用类型类的 IsClass 属性。如果类型是类，它将返回 true。否则，它将返回 false(对于结构或枚举数)。它是只读属性。

**语法**:

```cs
public bool IsClass { get; }
```

**例 1:**

## C#

```cs
// C# program to check the given 
// type is a class or not
using System;
using System.Reflection;

// Declare a class
public class Student1
{
    public void myfun()
    {
        Console.WriteLine("I like DSA");
    }
}

// Declare delegates
public delegate void divnum(int x, int y);

// Decalre structure
public struct Student2
{
    public int Id;
    public string Name;
}

public class GFG{

// Driver code
public static void Main(string[] args)
{

    // Check the given type is a class or not
    // Using IsClass property
    Console.WriteLine(typeof(Student1).IsClass);
    Console.WriteLine(typeof(divnum).IsClass);
    Console.WriteLine(typeof(Student2).IsClass);
}
}
```

**输出:**

```cs
True
True
False
```

**例 2:**

## C#

```cs
// C# program to check the given 
// type is a class or not
using System;
using System.Reflection;

// Declare a class
public class Pet
{
    public void myfun()
    {
        Console.WriteLine("I like Dogs");
    }
}

public class GFG{

// Driver code
public static void Main(string[] args)
{

    // Check the given type is a class or not
    // Using IsClass property
    if (typeof(Pet).IsClass == true)
    {
        Console.WriteLine("The given type is a class");
    }
    else
    {
        Console.WriteLine("The given type is not a class");
    }
}
}
```

**输出:**

```cs
The given type is a class
```