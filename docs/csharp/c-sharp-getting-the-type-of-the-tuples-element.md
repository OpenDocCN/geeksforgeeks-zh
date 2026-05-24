# C# |获取元组元素的类型

> 原文:[https://www . geeksforgeeks . org/c-sharp-get-type-of-the-tuples-element/](https://www.geeksforgeeks.org/c-sharp-getting-the-type-of-the-tuples-element/)

元组是一种数据结构，它为您提供了表示数据集的最简单方法。您可以使用**获取类型**方法获取元组对象的类型。这个方法将返回元组对象的类型。该方法继承自[对象类](https://www.geeksforgeeks.org/c-sharp-object-class/)。

**语法:**

```cs
public Type GetType ();
```

**返回类型:**此方法的返回类型为*类型*。意味着它返回元组< >对象的类型，其中元组< >可以是 1 元组、2 元组、3 元组、4 元组、5 元组、6 元组、7 元组或 8 元组。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the 
// use of GetType method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Taking 1-Tuple
        var v1 = Tuple.Create("Geeks");
        Console.WriteLine("Type of the element of 1-Tuple: " + v1.Item1.GetType());
        Console.WriteLine();

        // Taking 2-Tuple
        var v2 = Tuple.Create("GeeksforGeeks", 23);
        Console.WriteLine("Type of the First Element of 2-Tuple: " + v2.Item1.GetType());
        Console.WriteLine("Type of the Second Element of 2-Tuple: " + v2.Item2.GetType());
        Console.WriteLine();

        // Taking 3-Tuple
        var v3 = Tuple.Create("geeks", 234, 90.9);
        Console.WriteLine("Type of the First element of 3-Tuple: " + v3.Item1.GetType());
        Console.WriteLine("Type of the Second element of 3-Tuple: " + v3.Item2.GetType());
        Console.WriteLine("Type of the Third element of 3-Tuple: " + v3.Item3.GetType());
        Console.WriteLine();

        // Taking 4-Tuple
        var v4 = Tuple.Create("geeks", 567, 56.7, 'g');
        Console.WriteLine("Type of the First element of 3-Tuple: " + v4.Item1.GetType());
        Console.WriteLine("Type of the Second element of 3-Tuple: " + v4.Item2.GetType());
        Console.WriteLine("Type of the Third element of 3-Tuple: " + v4.Item3.GetType());
        Console.WriteLine("Type of the Fourth element of 3-Tuple: " + v4.Item4.GetType());

        // Taking 7-Tuple
        var v7 = Tuple.Create("geeks", 234.0, 90.9f, 56.6m, 67.8, true, 67.8);
        Console.WriteLine("Type of the First element of 7-Tuple: " + v7.Item1.GetType());
        Console.WriteLine("Type of the Second element of 7-Tuple: " + v7.Item2.GetType());
        Console.WriteLine("Type of the Third element of 7-Tuple: " + v7.Item3.GetType());
        Console.WriteLine("Type of the Fourth element of 7-Tuple: " + v7.Item4.GetType());
        Console.WriteLine("Type of the Fifth element of 7-Tuple: " + v7.Item5.GetType());
        Console.WriteLine("Type of the Sixth element of 7-Tuple: " + v7.Item6.GetType());
        Console.WriteLine("Type of the Seventh element of 7-Tuple: " + v7.Item7.GetType());
        Console.WriteLine();

    }
}
```

**Output:**

```cs
Type of the element of 1-Tuple: System.String

Type of the First Element of 2-Tuple: System.String
Type of the Second Element of 2-Tuple: System.Int32

Type of the First element of 3-Tuple: System.String
Type of the Second element of 3-Tuple: System.Int32
Type of the Third element of 3-Tuple: System.Double

Type of the First element of 3-Tuple: System.String
Type of the Second element of 3-Tuple: System.Int32
Type of the Third element of 3-Tuple: System.Double
Type of the Fourth element of 3-Tuple: System.Char
Type of the First element of 7-Tuple: System.String
Type of the Second element of 7-Tuple: System.Double
Type of the Third element of 7-Tuple: System.Single
Type of the Fourth element of 7-Tuple: System.Decimal
Type of the Fifth element of 7-Tuple: System.Double
Type of the Sixth element of 7-Tuple: System.Boolean
Type of the Seventh element of 7-Tuple: System.Double

```