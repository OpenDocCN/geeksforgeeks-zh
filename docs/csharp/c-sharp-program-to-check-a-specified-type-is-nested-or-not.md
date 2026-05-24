# 检查指定类型是否嵌套的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-check-a-specified-type-is-nested-or-not/](https://www.geeksforgeeks.org/c-sharp-program-to-check-a-specified-type-is-nested-or-not/)

在编程语言中，嵌套意味着类、方法、循环或结构存在于另一个类、方法、循环或结构中。在 C# 中，我们可以使用 type 类的 **IsNested** 属性来检查指定的类型是否嵌套。此属性返回一个值，该值表示指定的类型(即类、结构等)定义是否嵌套在另一个类型定义中。如果指定的类型是嵌套的，则返回真，否则返回假。

**语法:**

```cs
public bool IsNested { get; }
```

**例 1:**

## C#

```cs
// C# program to check a specified 
// type is nested or not
using System;
using System.Reflection;

// Create a structure
struct Geeks
{

    // Create a nested structure named Gfg2
    // with hello() method
    public struct Gfg2
    {
        void hello() 
        { 
            Console.WriteLine("hello geeks!"); 
        }
    }
}

class GFG{

// Driver code
static void Main()
{

    // Check the type is nested or not
    Console.WriteLine(typeof(Geeks.Gfg2).IsNested);
}
}
```

**输出:**

```cs
True
```

**例 2:**

## C#

```cs
// C# program to check a specified
// type is nested or not
using System;
using System.Reflection;

// Create a class
public class Geeks
{

    // Create a nested class
    // with hello() method
    public class Gfg2
    {
        void myfun() 
        { 
            Console.WriteLine("hello geeks!"); 
        }
    }
}

class GFG{

// Driver code
static void Main()
{

    // Check the type is nested or not
    if (typeof(Geeks.Gfg2).IsNested == true)
    {
        Console.WriteLine("Gfg2 class is nested class");
    }
    else
    {
        Console.WriteLine("Gfg2 class is not nested class");

    }
}
}
```

**输出:**

```cs
Gfg2 class is nested class
```