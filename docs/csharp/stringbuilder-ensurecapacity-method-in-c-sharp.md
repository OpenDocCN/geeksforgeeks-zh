# StringBuilder。C# 中的保证能力()方法

> 原文:[https://www . geeksforgeeks . org/stringbuilder-ensurecapacity-method-in-c-sharp/](https://www.geeksforgeeks.org/stringbuilder-ensurecapacity-method-in-c-sharp/)

StringBuilder 类的 EnsureCapacity(Int32)方法帮助我们确保容量至少等于作为参数传递给该方法的指定值。如果当前容量小于容量参数，则重新分配此实例的内存，以至少容纳容量数量的字符；否则，不会改变内存。

> **语法:**public int EnsureCapacity(int capacity)；
> 在这里，容量是保证的最小容量。
> 
> **返回值:**返回当前实例的新容量。

**异常:**如果容量小于零或扩大该实例的值会超过最大容量，该方法将给出*argumentout of range Exception*。

**例 1:**

```cs
// C# program to demonstrate
// the EnsureCapacity Method
using System;
using System.Text;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        // create a StringBuilder object
        StringBuilder str = new StringBuilder();

        // print string capacity
        Console.WriteLine("Before EnsureCapacity "
                          + "method capacity = "
                          + str.Capacity);

        // apply ensureCapacity()
        str.EnsureCapacity(18);

        // print string capacity
        Console.WriteLine("After EnsureCapacity"
                          + " method capacity = "
                          + str.Capacity);
    }
}
```

**Output:**

```cs
Before EnsureCapacity method capacity = 16
After EnsureCapacity method capacity = 18

```

**例 2:**

```cs
// C# program to demonstrate
// the EnsureCapacity Method
using System;
using System.Text;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        // create a StringBuilder object
        StringBuilder str = new StringBuilder();

        // print string capacity
        Console.WriteLine("Before EnsureCapacity "
                          + "method capacity = "
                          + str.Capacity);

        // apply ensureCapacity()
        str.EnsureCapacity(44);

        // print string capacity
        Console.WriteLine("After EnsureCapacity"
                          + " method capacity = "
                          + str.Capacity);
    }
}
```

**Output:**

```cs
Before EnsureCapacity method capacity = 16
After EnsureCapacity method capacity = 44

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . text . stringbuilder . ensurecapacity？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.ensurecapacity?view=netframework-4.7.2)