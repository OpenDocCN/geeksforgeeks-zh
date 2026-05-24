# 如何在 C# 中获取表示 ValueTuple 实例的字符串？

> 原文:[https://www . geeksforgeeks . org/如何获取表示-value tuple-instance-in-c-sharp/](https://www.geeksforgeeks.org/how-to-get-the-string-that-represents-valuetuple-instance-in-c-sharp/)

[ValueTuple](https://www.geeksforgeeks.org/valuetuple-in-c-sharp/) 是 C# 7.0 中引入的一个结构，代表值类型 Tuple。它允许您存储包含多个值的数据集，这些值可能彼此相关，也可能彼此不相关。借助**字符串方法**，还可以得到一个代表 ValueTuple 对象的字符串。此方法返回一个字符串，该字符串将表示 ValueTuple 对象。这种方法所代表的弦是 *()* 的形式。

**语法:**

```cs
public override string ToString ();
```

**返回类型:**该方法的返回类型为*系统。弦*。因此，它将返回一个表示 ValueTuple 对象的字符串。

**例 1:**

```cs
// C# program to illustrate 
// the use of ToString method
using System;

namespace exampleofvaluetuple {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // 1-ValueTuple
        var v1 = ("Rina");

        // Get the value of ValueTuple<T1>
        // With the help of ToString method
        Console.WriteLine("ValueTuple 1: " + v1.ToString());

        // 2-ValueTuple
        var v2 = ("Rohan", 25);

        // Get the value of ValueTuple<T1, T2>
        // With the help of ToString method
        Console.WriteLine("ValueTuple 2: " + v2.ToString());

        // 3-ValueTuple
        var v3 = ("Rima", 22, 2016);

        // Get the value of ValueTuple<T1, T2, T3>
        // With the help of ToString method
        Console.WriteLine("ValueTuple 3: " + v3.ToString());

        // 4-ValueTuple
        var v4 = ("Mohit", 28, 2014, "Junior Engineer");

        // Get the value of ValueTuple<T1, T2, T3, T4>
        // With the help of ToString method
        Console.WriteLine("ValueTuple 4: " + v4.ToString());

        // 5-ValueTuple
        var v5 = ("Rohit", 32, 2010, "CSE", "Junior Engineer");

        // Get the value of ValueTuple<T1, T2, T3, T4, T5>
        // With the help of ToString method
        Console.WriteLine("ValueTuple 5: " + v5.ToString());

        // 6-ValueTuple
        var v6 = ("Sunita", 25, 2015, "ECE",
                    "Junior Engineer", 102);

        // Get the value of ValueTuple<T1, T2,
        // T3, T4, T5, T6>
        // With the help of ToString method
        Console.WriteLine("ValueTuple 6: " + v6.ToString());

        // 7-ValueTuple
        var v7 = ("Sonu", 22, 2016, "CSE", 
        "Junior Engineer", 104, "C++");

        // Get the value of ValueTuple<T1, T2,
        // T3, T4, T5, T6, T7>

        // With the help of ToString method
        Console.WriteLine("ValueTuple 7: " + v7.ToString());

        // 8-ValueTuple
        var v8 = ("Susmita", 28, 2014, "Junior Engineer",
                109, "Java", ValueTuple.Create("Cricket", 
                            "Football", "Volleyball"));

        // Get the value of ValueTuple<T1, T2, T3,
        // T4, T5, T6, T7, TRest>
        // With the help of ToString method
        Console.WriteLine("ValueTuple 8: " + v8.ToString());
    }
}
}
```

**Output:**

```cs
ValueTuple 1: Rina
ValueTuple 2: (Rohan, 25)
ValueTuple 3: (Rima, 22, 2016)
ValueTuple 4: (Mohit, 28, 2014, Junior Engineer)
ValueTuple 5: (Rohit, 32, 2010, CSE, Junior Engineer)
ValueTuple 6: (Sunita, 25, 2015, ECE, Junior Engineer, 102)
ValueTuple 7: (Sonu, 22, 2016, CSE, Junior Engineer, 104, C++)
ValueTuple 8: (Susmita, 28, 2014, Junior Engineer, 109, Java, (Cricket, Football, Volleyball))

```

**例 2:**

```cs
// C# program to illustrate 
// the use of ToString method
using System;

namespace exampleofvaluetuple {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Nested Value Tuples
        var Emp1 = (Name: "Anu", Age : 23, 
          Languages: ValueTuple.Create("C++",
                    "Java", "Python", "C#"));

        var Emp2 = (Name: "Boond", Age : 27, Post: "Junior Engineer",
                        Languages: ValueTuple.Create("C++", "Java"));

        var Emp3 = (Name: "Rohit", Age : 25, Post: "HR",
                     Languages: ValueTuple.Create("C++", 
                                         "Java", "C#"));

        var Emp4 = (Name: "Mohan", Age : 26, Post: "Junior Engineer",
              Languages: ValueTuple.Create("C++", "Java", "Python"));

        // Get the value of Nested ValueTuples
        // With the help of ToString method
        Console.WriteLine("NValueTuple 1: {0}", Emp1.ToString());
        Console.WriteLine("NValueTuple 2: {0}", Emp2.ToString());
        Console.WriteLine("NValueTuple 3: {0}", Emp3.ToString());
        Console.WriteLine("NValueTuple 4: {0}", Emp4.ToString());
    }
}
}
```

**Output:**

```cs
NValueTuple 1: (Anu, 23, (C++, Java, Python, C#))
NValueTuple 2: (Boond, 27, Junior Engineer, (C++, Java))
NValueTuple 3: (Rohit, 25, HR, (C++, Java, C#))
NValueTuple 4: (Mohan, 26, Junior Engineer, (C++, Java, Python))

```