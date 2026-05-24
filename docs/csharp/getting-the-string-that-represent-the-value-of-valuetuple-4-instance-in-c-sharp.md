# 获取代表 C#

中 ValueTuple <t1>实例的值的字符串</t1>

> 原文:[https://www . geesforgeks . org/get-the-string-of-value-tuple-4-instance-in-c-sharp/](https://www.geeksforgeeks.org/getting-the-string-that-represent-the-value-of-valuetuple-4-instance-in-c-sharp/)

[ValueTuple](https://www.geeksforgeeks.org/valuetuple-in-c-sharp/) 是 C# 7.0 中引入的一个结构，代表值类型 Tuple。它允许您存储包含多个值的数据集，这些值可能彼此相关，也可能彼此不相关。您还可以在 ToString 方法的帮助下获得一个字符串，该字符串表示 ValueTuple 的对象的值。
此方法返回一个字符串，该字符串将表示 ValueTuple < T1、T2、T3、T4 >对象的值。这个方法表示的字符串是(项 1，项 2，项 3，项 4)的形式，这里项 1，项 2，项 3，项 4 表示项 1，项 2，项 3，项 4 属性的值，它将表示一个*字符串。如果任何属性包含空值，则为空*。

**语法:**

```cs
public override string ToString ();
```

**返回类型:**该方法的返回类型为*系统。弦*。因此，它将返回一个表示 ValueTuple < T1、T2、T3、T4 >对象的字符串。

**例 1:**

```cs
// C# program to illustrate the 
// use of ToString method
using System;

namespace exampleofvaluetuple{

    class GFG {

        // Main Method
        static void Main(string[] args)
        {

            // 1-ValueTuple
            var v1 = ValueTuple.Create("Rina");

            // Get the value of ValueTuple<T1>
            // With the help of ToString method
            Console.WriteLine("ValueTuple 1: " + v1.ToString());

            // 2-ValueTuple
            var v2 = ValueTuple.Create("Rohan", 25);

            // Get the value of ValueTuple<T1, T2>
            // With the help of ToString method
            Console.WriteLine("ValueTuple 2: " + v2.ToString());

            // 3-ValueTuple
            var v3 = ValueTuple.Create("Rima", 22, 2016);

            // Get the value of ValueTuple<T1, T2, T3>
            // With the help of ToString method
            Console.WriteLine("ValueTuple 3: " + v3.ToString());

            // 4-ValueTuple
            var v4 = ValueTuple.Create("Mohit", 28, 
                          2014, "Junior Engineer");

            // Get the value of ValueTuple<T1, T2, T3, T4>
            // With the help of ToString method
            Console.WriteLine("ValueTuple 4: " + v4.ToString());

        }
    }
}
```

**Output:**

```cs
ValueTuple 1: (Rina)
ValueTuple 2: (Rohan, 25)
ValueTuple 3: (Rima, 22, 2016)
ValueTuple 4: (Mohit, 28, 2014, Junior Engineer)

```

**例 2:**

```cs
// C# program to illustrate 
// the use of ToString method
using System;

namespace exampleofvaluetuple{

    class GFG {

        // Main Method
        static void Main(string[] args)
        {
            // Nested Value Tuples
            var Emp1 = (Name:"Anu", Age: 23, Languages:ValueTuple.Create("C++",
                                                      "Java", "Python", "C#"));

            var Emp2 = (Name:"Boond", Age:27, Post: "Junior Engineer",
                          Languages:ValueTuple.Create("C++", "Java"));

            var Emp3 = (Name: "Rohit", Age: 25, Post: "HR", 
                        Languages: ValueTuple.Create("C++",
                                            "Java", "C#"));

            var Emp4 = (Name: "Mohan", Age: 26, Post: "Junior Engineer",
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