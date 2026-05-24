# C# 程序检查一个类是否是指定类的子类

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-check-a-class-is-sub-class-of-specified-class-or-not/](https://www.geeksforgeeks.org/c-sharp-program-to-check-a-class-is-a-sub-class-of-a-specified-class-or-not/)

类是方法、变量和对象的集合。子类是从父类扩展而来的类。它应该实现父类的所有属性。它的语法类似于类。使用:运算符我们可以创建子类。我们可以通过使用 Type 类的 **IsSubclassOf()** 方法来检查该类是否是特定类的子类。或者我们可以说 IsSubclassOf()方法用于检查当前类型是否是从给定类型派生的。如果子类特定于父类，它将返回 true。否则，它将返回 false。当类名为空类型时，这个方法会抛出 *ArgumentNullException* 。该方法用于:

*   检查该类是否派生自另一个类。
*   检查类型是否从值类型派生。
*   检查该类型是否从枚举派生。
*   检查类型是否从委托派生。

**语法**:

```cs
public virtual bool IsSubclassOf(Type c);
```

**例 1:**

## C#

```cs
// C# program to check whether a class is
// a sub-class of a specified class or not
using System;

// Create a class named Geeks
public class Geeks{}

// Create a subclass that is from Geeks class
public class smallGFG : Geeks{}

// Create a class named mygg
public class mygg{}

class GFG{

// Drived code
public static void Main()
{

    // Check the class is a subclass of the class
    // Using IsSubclassOf() method
    Console.WriteLine(typeof(smallGFG).IsSubclassOf(typeof(Geeks)));
    Console.WriteLine(typeof(Geeks).IsSubclassOf(typeof(smallGFG)));
    Console.WriteLine(typeof(mygg).IsSubclassOf(typeof(Geeks)));
}
}
```

**输出:**

```cs
True
False
False
```

**例 2:**

## C#

```cs
// C# program to check whether a class is
// a sub-class of a specified class or not
using System;

// Create a class named Geeks
public class Mypet
{
    public void color()
    {
        Console.WriteLine("I like pink color hair");
    }
}

// Create a subclass that is from Mypet class
public class Dog : Mypet{}

class GFG{

// Driver code
public static void Main()
{

    // Check the class is a subclass of the class
    // Using IsSubclassOf() method
    if (typeof(Dog).IsSubclassOf(typeof(Mypet)) == true)
    {
        Console.WriteLine("Given class is a sub class");
    }
    else
    {
        Console.WriteLine("Given class is not a sub class");
    }
}
}
```

**输出:**

```cs
Given class is a sub class
```