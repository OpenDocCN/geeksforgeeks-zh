# 获取代表 C#

中元组<t1>实例值的字符串</t1>

> 原文:[https://www . geeksforgeeks . org/get-the-string-表示-tuple-1-instance-in-c-sharp/](https://www.geeksforgeeks.org/getting-the-string-that-represent-the-value-of-the-tuple-1-instance-in-c-sharp/)

一个[元组](https://www.geeksforgeeks.org/c-sharp-tuple/)是一个数据结构，它给你最简单的方法来表示一个数据集。您也可以通过使用**字符串方法**来获取表示元组对象的字符串。该方法返回一个表示**元组<T1>T5】对象的字符串。此方法表示的字符串采用(Item1)的形式，这里 Item1 表示 Item1 属性值。它将代表一根*弦。如果任何属性包含空值，则为空*。**

**语法:**

```cs
public override string ToString ();
```

**返回类型:**该方法的返回类型为*系统。弦*。因此，它将返回一个表示 Tuple < T1 >对象的字符串。

**例 1:**

```cs
// C# program to illustrate the
// use of ToString method
using System;

namespace exampleoftuple {

class GFG {

    // Main Method
    static void Main(string[] args)
    {   

        // 1-Tuple
        var v1 = Tuple.Create("Rohit");

         // Get the value of Tuple<T1>
        // With the help of ToString method
        Console.WriteLine("Tuple 1: " + v1.ToString());
    }
}
}
```

**Output:**

```cs
Tuple 1: (Rohit)

```

**例 2:**

```cs
// C# program to illustrate 
// the use of ToString method
using System;

namespace exampleoftuple {

class GFG {

    // Main Method
    static public void Main()
    {
        // Nested Tuples
        var T1 = Tuple.Create("Sumit", Tuple.Create("Bongo",
                                          "Bella", "Binu"));

        var T2 = Tuple.Create("Boond", "Cinki", "Chimmy",
                         Tuple.Create("Karan", "Micky"));

        var T3 = Tuple.Create(34.9, 78.7, Tuple.Create(12.2,
                                           34.5, 5.6, .78));

        var T4 = Tuple.Create(2, 4, 6, 8, 5,
           Tuple.Create(10, 20, 30, 40, 50));

        // Get the value of Nested Tuples
        // With the help of ToString method
        Console.WriteLine("NTuple 1: {0}", T1.ToString());
        Console.WriteLine("NTuple 2: {0}", T2.ToString());
        Console.WriteLine("NTuple 3: {0}", T3.ToString());
        Console.WriteLine("NTuple 4: {0}", T4.ToString());
    }
}
}
```

**Output:**

```cs
NTuple 1: (Sumit, (Bongo, Bella, Binu))
NTuple 2: (Boond, Cinki, Chimmy, (Karan, Micky))
NTuple 3: (34.9, 78.7, (12.2, 34.5, 5.6, 0.78))
NTuple 4: (2, 4, 6, 8, 5, (10, 20, 30, 40, 50))

```