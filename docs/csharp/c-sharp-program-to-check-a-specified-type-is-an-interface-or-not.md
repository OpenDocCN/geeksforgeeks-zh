# 检查指定类型的 C# 程序是否是接口

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-check-a-specified-type-is-a-interface-or-not/](https://www.geeksforgeeks.org/c-sharp-program-to-check-a-specified-type-is-an-interface-or-not/)

接口就像一个类，它也可以有方法、属性、事件等。但是它只包含成员的声明，这些成员的实现将由隐式或显式实现接口的类给出。我们可以通过使用类型类的 IsInterface 属性来检查指定的类型是否是接口。如果给定的类型是接口，它将返回 true。否则，它将返回 false。它是只读属性。

**语法**:

```cs
public bool IsInterface { get; }
```

**例 1:**

## C#

```cs
// C# program to check whether the 
// given type is interface or not
using System;
using System.Reflection;

// Declare an interface
interface myinterface
{

    // Method in interface
    void gfg();
}

class GFG{

// Driver code
static void Main()
{

    // Check the type is interface or not
    // Using the IsInterface property
    if (typeof(myinterface).IsInterface == true) 
    {
        Console.WriteLine("Yes it is Interface");
    }
    else 
    {
        Console.WriteLine("No it is not an Interface");
    }
}
}
```

**输出:**

```cs
Yes it is Interface
```

**例 2:**

## C#

```cs
// C# program to check whether the 
// given type is interface or not
using System;
using System.Reflection;

// Declare an interface
interface myinterface
{

    // Method in interface
    void gfg();
}

// Declare a class
public class myclass
{
    public void myfunc(){}
}

// Declare a struct
public struct mystruct
{
    int a;
}

class GFG{

// Driver code
static void Main()
{

    // Check the type is interface or not
    // Using the IsInterface property
    Console.WriteLine(typeof(myinterface).IsInterface);
    Console.WriteLine(typeof(myclass).IsInterface);
    Console.WriteLine(typeof(mystruct).IsInterface);
}
}
```

**输出:**

```cs
True
False
False
```