# 检查指定类型是否公开的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-check-a-specified-type-is-public-or-not/](https://www.geeksforgeeks.org/c-sharp-program-to-check-a-specified-type-is-public-or-not/)

类是方法、变量和对象的集合。我们可以使用[访问修饰符](https://www.geeksforgeeks.org/access-modifiers-in-c-sharp/)创建公共类、私有类或受保护类。用 public 修饰符创建的类将可以完全访问一个程序。因此，为了检查给定的类或类型是否是公共类型，我们使用类型类的 IsPublic 属性。如果给定类型是公共类型，它将返回 true。否则，它将返回 false。此外，此属性不适用于嵌套类型。

**语法:**

```cs
public bool IsPublic { get; }
```

**例 1:**

## C#

```cs
// C# program to check whether the given class or
// type is a public type or not
using System;
using System.Reflection;

// Declare a class with public modifier
public class Myclass1
{
    public void display()
    {
        Console.WriteLine("Hello! GeeksforGeeks");
    }
}

// Declare a class without public modifier
class Myclass2
{
    public void Show()
    {
        Console.WriteLine("Hey! GeeksforGeeks");
    }
}

public class GFG{

// Driver code    
public static void Main(string[] args)
{

    // Check the given type is a public or not
    // Using IsPublic property
    Console.WriteLine(typeof(Myclass1).IsPublic);
    Console.WriteLine(typeof(Myclass2).IsPublic);
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
// C# program to check whether the given class or
// type is a public type or not
using System;
using System.Reflection;

// Declare a class with public modifier
public class Student
{
    public void display()
    {
        Console.WriteLine("I like C# languagea alot");
    }
}

public class GFG{

// Driver code    
public static void Main(string[] args)
{

    // Check the given type is a public or not
    // Using IsPublic property
    if (typeof(Student).IsPublic == true)
    {
        Console.WriteLine("The given class is a public class");
    }
    else
    {
        Console.WriteLine("The given class is not a public class");
    }
}
}
```

**输出:**

```cs
The given class is a public class
```