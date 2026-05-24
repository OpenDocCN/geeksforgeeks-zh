# 在 C# 中比较两个值元组

> 原文:[https://www . geesforgeks . org/comparising-two-value tuple-2 in-c-sharp/](https://www.geeksforgeeks.org/comparing-two-valuetuple-2-in-c-sharp/)

[ValueTuple](https://www.geeksforgeeks.org/valuetuple-in-c-sharp/) 是 C# 7.0 中引入的一个结构，代表值类型 Tuple。它已经包含在中。. NET Framework 4.7 或更高版本。它允许您存储包含多个值的数据集，这些值可能彼此相关，也可能彼此不相关。
还可以使用 **CompareTo(ValueTuple < T1，T2 >)方法**来比较两个值元组的实例。或者换句话说，借助 CompareTo 方法，您可以将 T2 的当前 value tuple<T1>实例与指定的 [ValueTuple < T1、T2 的>T6】实例进行比较。此方法还将嵌套值元组相互比较。](https://www.geeksforgeeks.org/c-sharp-valuetuple-2-struct/)

**语法:**

```cs
public int CompareTo (ValueTuple<T1, T2> other);

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
        // 2-ValueTuple
        var t1 = (43, 34);
        var t2 = (78, 98);
        Console.WriteLine("Result 1: {0}", t1.CompareTo(t2));

        // 2-ValueTuple
        var p1 = (86, 99);
        var p2 = (44, 22);
        Console.WriteLine("Result 2: {0}", p1.CompareTo(p2));

        // 2-ValueTuple
        var q1 = (10, 20);
        var q2 = (10, 20);
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
        // 2-ValueTuple
        var t1 = (44, 34);
        var t2 = (44, 45);

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
Value tuples are not equal!!

```