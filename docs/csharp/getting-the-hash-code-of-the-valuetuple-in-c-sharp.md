# 获取 C# 中 ValueTuple 的哈希代码

> 原文:[https://www . geesforgeks . org/get-the-hash-code-of-value tuple-in-c-sharp/](https://www.geeksforgeeks.org/getting-the-hash-code-of-the-valuetuple-in-c-sharp/)

**ValueTuple。GetHashCode 方法**用于获取当前 [ValueTuple](https://www.geeksforgeeks.org/valuetuple-in-c-sharp/) 实例的 HashCode。它由 ValueTuple 结构提供。

**语法:**

```cs
public override int GetHashCode ();
```

**返回:**该方法的返回类型为系统。Int32，它总是返回零。

**示例:**

```cs
// C# program to illustrate how to
// find the hash code of the given 
// value tuples.
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating a value tuple with zero element
        var MyTple1 = ValueTuple.Create();
        Console.WriteLine("HashCode of a value tuple with"+
               " zero elements: " + MyTple1.GetHashCode());

        // Creating a value tuple with one element
        var MyTple2 = (23);
        Console.WriteLine("HashCode of a value tuple "+
            "with one element: " + MyTple2.GetHashCode());

        // Creating a value tuple with two elements
        var MyTple3 = (56, 45);
        Console.WriteLine("HashCode of a value tuple "+
           "with two elements: " + MyTple3.GetHashCode());

        // Creating a value tuple with three elements
        var MyTple4 = (67, 78, 89);
        Console.WriteLine("HashCode of a value tuple with "+
                "three elements: " + MyTple4.GetHashCode());

        // Creating a value tuple with four elements
        var MyTple5 = (09, 23, 12, 1);
        Console.WriteLine("HashCode of a value tuple with "+
                 "four elements: " + MyTple5.GetHashCode());

        // Creating a value tuple with five elements
        var MyTple6 = (65, 87, 98, 23, 45);
        Console.WriteLine("HashCode of a value tuple with"+
               " five elements: " + MyTple6.GetHashCode());

        // Creating a value tuple with six elements
        var MyTple7 = (13, 56, 78, 12, 65, 98);
        Console.WriteLine("HashCode of a value tuple with"+
                " six elements: " + MyTple7.GetHashCode());

        // Creating a value tuple with seven elements
        var MyTple8 = (32, 45, 96, 78, 35, 33, 44);
        Console.WriteLine("HashCode of a value tuple with"+
              " seven elements: " + MyTple8.GetHashCode());
    }
}
```

**Output:**

```cs
HashCode of a value tuple with zero elements: 0
HashCode of a value tuple with one element: 23
HashCode of a value tuple with two elements: -818407567
HashCode of a value tuple with three elements: -1237760639
HashCode of a value tuple with four elements: 2105592814
HashCode of a value tuple with five elements: 695326364
HashCode of a value tuple with six elements: -335480823
HashCode of a value tuple with seven elements: -2111090807

```