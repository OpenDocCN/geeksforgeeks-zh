# 检查指定类型是否为值类型的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-check-a-specified-type-is-a-value-type-or-not/](https://www.geeksforgeeks.org/c-sharp-program-to-check-a-specified-type-is-a-value-type-or-not/)

在 C# 中，值类型表示一个位序列。它不是类或接口，它被称为结构或枚举(值类型的特例)。因此，为了检查指定的类型是否是值类型，我们使用类型类的 is Value Type 属性。它是只读属性。如果类型是值类型，它将返回真。否则，它将返回 false。它将为枚举返回真，但不会为枚举类型返回真。

**语法**:

```cs
public bool IsValueType { get; }
```

**例 1:**

## C#

```cs
// C# program to check whether the specified
// type is a value type or not
using System;
using System.Reflection;

// Declare a structure
struct myStructure
{

    // Declaring a method 
    public static void display()
    {
        Console.WriteLine("Hello! GeeksforGeeks");
    }
}

// Declare a class
public class Geeks
{

    // Declaring a method 
    public static void show()
    {
        Console.WriteLine("Hey! GeeksforGeeks");
    }

}

public class GFG{

// Driver class
public static void Main(string[] args)
{

    // Checking the given type is a value type or not
    // Using IsValueType Property
    Console.WriteLine(typeof(myStructure).IsValueType);
    Console.WriteLine(typeof(Geeks).IsValueType);
}
}
```

**输出:**

```cs
True
False
```

**例 2:**

## C#

```cs
// C# program to check whether the specified
// type is a value type or not
using System;
using System.Reflection;

// Declare a structure
struct myGFG
{

    // Declaring a method 
    public static void display()
    {
        Console.WriteLine("Welcome to GeeksforGeeks");
    }
}

public class GFG{

// Driver class
public static void Main(string[] args)
{

    // Checking the given type is a value type or not
    // Using IsValueType Property
    if (typeof(myGFG).IsValueType == true)
    {
        Console.WriteLine("The given type is value type");
    }
    else
    {
        Console.WriteLine("The given type is not a value type");
    }
}
}
```

**输出:**

```cs
The given type is value type
```