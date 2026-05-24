# C# |如何获取元组的 HashCode？

> 原文:[https://www . geeksforgeeks . org/c-sharp-如何获取元组哈希码/](https://www.geeksforgeeks.org/c-sharp-how-to-get-the-hashcode-of-the-tuple/)

元组是一种数据结构，它为您提供了表示数据集的最简单方法。也可以使用 **GetHashCode 方法**获取元组的哈希码。此方法将返回给定元组对象的哈希代码。

**语法:**

```cs
public override int GetHashCode ();
```

**返回类型:**该方法的返回类型为*系统。Int32* 。它将返回 32 位有符号整数哈希代码。

**例 1:**

```cs
// C# program to illustrate the 
// use of GetHashCode method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // creating different tuples using Create Method
        var tu1 = Tuple.Create(23, 45, 78, 89, 56);
        var tu2 = Tuple.Create(34, 45);
        var tu3 = Tuple.Create(45, 454, 454, 545, 4, 544, 54, 56);
        var tu4 = Tuple.Create(44, 58, 66, 32);

        // Get the hash code of the Tuples
        // Using GetHashCode method
        Console.WriteLine("HashCode for tu1: " + tu1.GetHashCode());
        Console.WriteLine("HashCode for tu2: " + tu2.GetHashCode());
        Console.WriteLine("HashCode for tu3: " + tu3.GetHashCode());
        Console.WriteLine("HashCode for tu4: " + tu4.GetHashCode());
    }
}
```

**Output:**

```cs
HashCode for tu1: 712149
HashCode for tu2: 1103
HashCode for tu3: 1582758
HashCode for tu4: 45300

```

**例 2:**

```cs
// C# program to illustrate the use 
// of the GetHashCode method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating different Tuples
        // using Create Method
        var t1 = Tuple.Create(64, 76, 78, Tuple.Create(12, 34, 56, 78));

        var t2 = Tuple.Create(78, 34, 86, Tuple.Create(23, 56));

        var t3 = Tuple.Create(34, 78, Tuple.Create(12, 34, 56, 78));

        var t4 = Tuple.Create(12, 34, 56, 34, 56, 65, 78,
                   Tuple.Create(24, 45, 67, 78, 89, 88));

        // Get the hash code of the Tuples
        // Using GetHashCode method
        Console.WriteLine("HashCode for t1: " + t1.GetHashCode());
        Console.WriteLine("HashCode for t2: " + t2.GetHashCode());
        Console.WriteLine("HashCode for t3: " + t3.GetHashCode());
        Console.WriteLine("HashCode for t4: " + t4.GetHashCode());
    }
}
```

**Output:**

```cs
HashCode for t1: 78746
HashCode for t2: 83573
HashCode for t3: 47540
HashCode for t4: 672122

```