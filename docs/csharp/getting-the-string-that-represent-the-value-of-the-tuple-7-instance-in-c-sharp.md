# 获取代表 C#

中元组<t1>实例值的字符串</t1>

> 原文:[https://www . geeksforgeeks . org/get-the-string-表示-tuple-7-instance-in-c-sharp/](https://www.geeksforgeeks.org/getting-the-string-that-represent-the-value-of-the-tuple-7-instance-in-c-sharp/)

一个[元组](https://www.geeksforgeeks.org/c-sharp-tuple/)是一个数据结构，它给你最简单的方法来表示一个数据集。您也可以通过使用**字符串方法**来获取表示元组对象的字符串。该方法返回一个字符串，该字符串将表示元组< T1、T2、T3、T4、T5、T6、T7 >对象。此方法表示的字符串的形式为(项 1、项 2、项 3、项 4、项 5、项 6、项 7)这里项 1、项 2、项 3、项 4、项 5、项 6、项 7 表示项 1、项 2、项 3、项 4、项 5、项 6、项 7 的属性值。它将代表一根*弦。如果任何属性包含空值，则为空*。

**语法:**

```cs
public override string ToString ();
```

**返回类型:**该方法的返回类型为*系统。弦*。因此，它将返回一个表示 Tuple < T1、T2、T3、T4、T5、T6、T7 >对象的字符串。

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

        // 2-Tuple
        var v2 = Tuple.Create("Sheema", "Riya");

        // Get the value of Tuple<T1, T2>
        // With the help of ToString method
        Console.WriteLine("Tuple 2: " + v2.ToString());

        // 3-Tuple
        var v3 = Tuple.Create("Rima", "Suman", "Sohan");

        // Get the value of Tuple<T1, T2, T3>
        // With the help of ToString method
        Console.WriteLine("Tuple 3: " + v3.ToString());

        // 4-Tuple
        var v4 = Tuple.Create("Shilpa", "Susma",
                              "Sumit", "Rohan");

        // Get the value of Tuple<T1, T2, T3, T4>
        // With the help of ToString method
        Console.WriteLine("Tuple 4: " + v4.ToString());
    }
}
}
```

**Output:**

```cs
Tuple 1: (Rohit)
Tuple 2: (Sheema, Riya)
Tuple 3: (Rima, Suman, Sohan)
Tuple 4: (Shilpa, Susma, Sumit, Rohan)

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

        // 5-Tuple
        var v5 = Tuple.Create(2, 4, 6, 8, 10);

        // Get the value of Tuple<T1, T2, T3, T4, T5>
        // With the help of ToString method
        Console.WriteLine("Tuple 5: " + v5.ToString());

        // 6-Tuple
        var v6 = Tuple.Create(3, 6, 9, 12, 15, 18);

        // Get the value of Tuple<T1, T2, T3, T4, T5, T6>
        // With the help of ToString method
        Console.WriteLine("Tuple 6: " + v6.ToString());

        // 7-Tuple
        var v7 = Tuple.Create(12, 45, 67, 78, 87, 97, 87);

        // Get the value of Tuple<T1, T2, T3, T4, T5, T6, T7>
        // With the help of ToString method
        Console.WriteLine("Tuple 7: " + v7.ToString());
    }
}
}
```

**Output:**

```cs
Tuple 5: (2, 4, 6, 8, 10)
Tuple 6: (3, 6, 9, 12, 15, 18)
Tuple 7: (12, 45, 67, 78, 87, 97, 87)

```