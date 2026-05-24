# 检查指定类的 C# 程序是否为可序列化类

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-check-a-specified-class-is-serializable-class-or-not/](https://www.geeksforgeeks.org/c-sharp-program-to-check-a-specified-class-is-a-serializable-class-or-not/)

序列化是一种将对象转换成字节流的方法，字节流将用于将对象存储在数据库、内存或文件等中，以便我们可以轻松地读回并将其转换回对象。因此，为了检查指定的类是否可序列化，我们使用类型类的 is serializable 属性。如果该类被声明为可序列化，它将返回 true。否则，它将返回 false。

**语法:**

```cs
public bool IsSerializable { get; }
```

**例 1:**

## C#

```cs
// C# program to check whether the given
// class is serializable class or not
using System;
using System.Reflection;

// Declare a serializable class
[Serializable] class Geeks1
{
    public static void Display()
    {
        Console.WriteLine("Hello! Geeks1");
    }
}

// Declare a normal class
class Geeks2
{
    public static void Show()
    {
        Console.WriteLine("Hello! Geeks2");
    }
}

class GFG{

// Driver code    
static void Main()
{

    // Check the specific class is Serializable or not
    Console.WriteLine("Is Geeks1 class is serializable or not?:" + 
                      typeof(Geeks1).IsSerializable);
    Console.WriteLine("Is Geeks2 class is serializable or not?:" + 
                      typeof(Geeks2).IsSerializable);
}
}
```

**输出:**

```cs
Is Geeks1 class is serializable or not?:True
Is Geeks2 class is serializable or not?:False
```

**例 2:**

## C#

```cs
// C# program to check whether the given
// class is serializable class or not
using System;
using System.Reflection;

// Declare a serializable class
[Serializable] class Geeks
{
    public static void Display()
    {
        Console.WriteLine("Hello");
    }
}

class GFG{

// Driver code    
static void Main()
{

    // Checking the class is serializable or not
    // Using IsSerializable property
    if (typeof(Geeks).IsSerializable == true)
    {
        Console.WriteLine("The given class is serializable");
    }
    else
    {
        Console.WriteLine("The given class is not serializable");
    }
}
}
```

**输出:**

```cs
The given class is serializable
```