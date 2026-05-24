# C# | CharEnumerator。GetType()方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-charenumerator-gettype-method/](https://www.geeksforgeeks.org/c-sharp-charenumerator-gettype-method/)

**CharEnumerator。GetType()方法**用于获取当前实例的类型。此方法继承自对象类。

**语法:**

```cs
public Type GetType();
```

**返回值:**此方法返回当前实例的确切运行时类型。

下面是说明使用**字符枚举器的程序。GetType()** 方法:+

**例 1:**

```cs
// C# program to illustrate the
// use of CharEnumerator.GetType()
// Method
using System;

class GFG {

    // Driver code
    public static void Main()
    {
        // Initialize a string object
        string str = "GeeksforGeeks is Awesome!";

        // Instantiate a CharEnumerator object
        CharEnumerator chEnum = str.GetEnumerator();

        // Printing the Type of
        // the CharEnumerator objects
        Console.WriteLine(chEnum.GetType());
    }
}
```

**Output:**

```cs
System.CharEnumerator

```

**例 2:**

```cs
// C# program to illustrate the
// use of CharEnumerator.GetType()
// Method
using System;

class GFG {

    // Driver code
    public static void Main()
    {
        // Initialize a string object
        string str = "GeeksforGeeks is fun";

        // Instantiate a CharEnumerator object
        CharEnumerator chEnum = str.GetEnumerator();

        // Instantiate a clone of CharEnumerator object
        CharEnumerator chEnumClone = (CharEnumerator)chEnum.Clone();

        // Printing the Type of the
        // CharEnumerator objects and its clone
        Console.WriteLine("Type of CharEnumerator object: "
                                       + chEnum.GetType());

        Console.WriteLine("Type of CharEnumerator clone object: " 
                                        + chEnumClone.GetType());
    }
}
```

**Output:**

```cs
Type of CharEnumerator object: System.CharEnumerator
Type of CharEnumerator clone object: System.CharEnumerator

```