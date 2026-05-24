# 在 C# 中比较两个值元组

> 原文:[https://www . geesforgeks . org/comparising-two-value tuple-8 in-c-sharp/](https://www.geeksforgeeks.org/comparing-two-valuetuple-8-in-c-sharp/)

[ValueTuple](https://www.geeksforgeeks.org/valuetuple-in-c-sharp/) 是 C# 7.0 中引入的一个结构，代表值类型 Tuple。它已经包含在中。. NET Framework 4.7 或更高版本。它允许您存储包含多个值的数据集，这些值可能彼此相关，也可能彼此不相关。
您也可以使用 **CompareTo(ValueTuple < T1、T2、T3、T4、T5、T6、T7、TRest >)方法**来比较两个值元组的实例。或者换句话说，借助 CompareTo 方法，您可以将当前的 [ValueTuple < T1、T2、T3、T4、T5、T6、T7、TRest >](https://www.geeksforgeeks.org/c-sharp-valuetuple-8-struct/) 实例与指定的 ValueTuple < T1、T2、T3、T4、T5、T6、T7、TRest >实例进行比较。此方法还将嵌套值元组相互比较。

**语法:**

```cs
public int CompareTo (ValueTuple other);

```

**返回类型:**该方法的返回类型为*系统。Int32* 。并且它总是返回一个有符号整数，该整数指示此实例和其他实例在排序顺序中的相对位置，如下列表所示:

*   实例的负整数在另一个之前。
*   实例的零和其他零在排序顺序中具有相同的位置。
*   实例的正整数跟在另一个之后。

**例 1:**

```cs
// C# program to illustrate the 
// use of CompareTo method
using System;

namespace exampleofvaluetuple {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // 8-ValueTuple
        var t1 = ValueTuple.Create(43, 34, 22, 7, 8,
                29, 30, ValueTuple.Create(1, 2, 3));

        var t2 = ValueTuple.Create(78, 98, 76, 67, 54,
               78, 89, ValueTuple.Create(10, 22, 30));

        Console.WriteLine("Result 1: {0}", t1.CompareTo(t2));

        // 8-ValueTuple
        var p1 = ValueTuple.Create(86, 99, 67, 88, 89,
               96, 78, ValueTuple.Create(90, 80, 70));

        var p2 = ValueTuple.Create(44, 22, 06, 55, 12, 
                  16, 23, ValueTuple.Create(9, 8, 7));

        Console.WriteLine("Result 2: {0}", p1.CompareTo(p2));

        // 8-ValueTuple
        var q1 = ValueTuple.Create(10, 20, 30, 40, 50,
               60, 70, ValueTuple.Create(22, 33, 44));

        var q2 = ValueTuple.Create(10, 20, 30, 40, 50,
               60, 70, ValueTuple.Create(22, 33, 44));

        Console.WriteLine("Result 3: {0}", q1.CompareTo(q2));
    }
}
}
```

**Output:**

```cs
Result 1: -1
Result 2: 1
Result 3: 0

```

**例 2:**

```cs
// C# program to illustrate the
// use of CompareTo method
using System;

namespace exampleofvaluetuple {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // 8-ValueTuple
        var t1 = ValueTuple.Create(44, 55, 66, 77, 88,
                  99, 33, ValueTuple.Create(1, 2, 3));

        var t2 = ValueTuple.Create(44, 55, 66, 77, 88, 
                  99, 33, ValueTuple.Create(1, 2, 3));

        // Using CompareTo Method
        if (t1.CompareTo(t2) == 0) {

            Console.WriteLine("Value tuples are equal!!");
        }

        else {

            Console.WriteLine("Value tuples are not equal!!");
        }
    }
}
}
```

**Output:**

```cs
Value tuples are equal!!

```