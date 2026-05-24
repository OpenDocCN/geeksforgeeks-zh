# 获取代表 C#

中 ValueTuple <t1>实例的值的字符串</t1>

> 原文:[https://www . geesforgeks . org/get-the-string-of-value-tuple-6-instance-in-c-sharp/](https://www.geeksforgeeks.org/getting-the-string-that-represent-the-value-of-valuetuple-6-instance-in-c-sharp/)

[ValueTuple](https://www.geeksforgeeks.org/valuetuple-in-c-sharp/) 是 C# 7.0 中引入的一个结构，代表值类型 Tuple。它允许您存储包含多个值的数据集，这些值可能彼此相关，也可能彼此不相关。您也可以在**字符串方法**的帮助下获得一个代表 ValueTuple 对象的值的字符串。
此方法返回一个字符串，该字符串将表示 ValueTuple < T1、T2、T3、T4、T5、T6 >对象的值。该方法表示的字符串形式为(项 1、项 2、项 3、项 4、项 5、项 6)这里项 1、项 2、项 3、项 4、项 5、项 6 表示项 1、项 2、项 3、项 4、项 5、项 6 属性的值，它将表示一个*字符串。如果任何属性包含空值，则为空*。

**语法:**

```cs
public override string ToString ();
```

**返回类型:**该方法的返回类型为*系统。弦*。因此，它将返回一个表示 ValueTuple < T1、T2、T3、T4、T5、T6 >对象的字符串。

**例 1:**

```cs
// C# program to illustrate 
// the use of ToString method
using System;

namespace exampleofvaluetuple{

    class GFG{

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
            var v4 = ValueTuple.Create("Mohit", 28, 2014, "Junior Engineer");

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
// C# program to illustrate the 
// use of ToString method
using System;

namespace exampleofvaluetuple{

    class GFG {

        // Main Method
        static void Main(string[] args)
        {
            // 5-ValueTuple
            var v5 = ValueTuple.Create("Rohit", 32, 
                   2010, "CSE", "Junior Engineer");

            // Get the value of ValueTuple<T1,
            // T2, T3, T4, T5>
            // With the help of ToString method
            Console.WriteLine("ValueTuple 5: "+v5.ToString());

            // 6-ValueTuple
            var v6 = ValueTuple.Create("Sunita", 25, 2015,
                           "ECE", "Junior Engineer", 102);

            // Get the value of ValueTuple<T1, T2, T3, T4, T5, T6>
            // With the help of ToString method
            Console.WriteLine("ValueTuple 6: "+v6.ToString());

        }
    }
}
```

**Output:**

```cs
ValueTuple 5: (Rohit, 32, 2010, CSE, Junior Engineer)
ValueTuple 6: (Sunita, 25, 2015, ECE, Junior Engineer, 102)

```