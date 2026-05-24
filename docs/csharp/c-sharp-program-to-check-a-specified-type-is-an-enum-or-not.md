# 检查指定类型是否为枚举的 C# 程序

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-check-a-specified-type-is-enum-or-not/](https://www.geeksforgeeks.org/c-sharp-program-to-check-a-specified-type-is-an-enum-or-not/)

[枚举](https://www.geeksforgeeks.org/c-sharp-enumeration-or-enum/)或也称为枚举，用于存储用户定义的数据。它用于将字符串值赋给一个整数常量，这使得程序易于读取和管理。我们可以使用 enum 关键字后跟 enum 名称来创建 enum 数据。在 C# 中，我们可以通过使用 type 类的 is enum 属性来检查具体的类型是枚举还是非枚举。如果类型是枚举，它将返回 true。否则，此属性将返回 false。它是只读属性。

**语法:**

```cs
public bool IsEnum { get; }
```

**返回类型:**该属性的返回类型为布尔值。它将返回真或假。

**例 1:**

## C#

```cs
// C# program to check whether the
// given type is enum or not
using System;
using System.Reflection;

// Declare a enum type with subjects
enum Subject
{
    Java, Python, Php, Html
}

class GFG{

// Driver code  
public static void Main(string[] args)
{

    // Check the given type is a enum or not
    // Using IsEnum property
    Console.WriteLine(typeof(Subject).IsEnum);
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
// C# program to check whether the
// given type is enum or not
using System;
using System.Reflection;

enum courses
{
    DSA, ReactJS, OperatingSystem, DBMS
}

class Branch
{
    void display()
    {
        Console.WriteLine("Name of the branch");
    }
}

struct subject
{
    string name;
    int marks;
}

class GFG{

// Driver code  
public static void Main(string[] args)
{

    // Check the given type is a enum or not
    // Using IsEnum property
    bool res1 = typeof(courses).IsEnum;
    bool res2 = typeof(Branch).IsEnum;
    bool res3 = typeof(subject).IsEnum;

    Console.WriteLine("Is courses is enum?: " + res1);
    Console.WriteLine("Is Branch is enum?: " + res2);
    Console.WriteLine("Is subject is enum?: " + res3);
}
}
```

**输出:**

```cs
Is courses is enum?: True
Is Branch is enum?: False
Is subject is enum?: False
```