# 如何在 C# 中比较两个 ValueTuple？

> 原文:[https://www . geeksforgeeks . org/how-to-compare-two-value tuple in-c-sharp/](https://www.geeksforgeeks.org/how-to-compare-two-valuetuple-in-c-sharp/)

要比较 [ValueTuple](https://www.geeksforgeeks.org/valuetuple-in-c-sharp/) 的两个实例，可以使用 ValueTuple 结构提供的 CompareTo 方法。**值元组。CompareTo(ValueTuple)方法**用于将 ValueTuple 的当前实例与另一个 ValueTuple 实例进行比较。如果它们彼此相等，它总是返回零。

**语法:**

```cs
public int CompareTo (ValueTuple other);
```

这里，*其他*是与当前实例比较的对象。

**返回:**该方法始终返回 System.Int32 类型的 0

**异常:**如果*其他*不是 ValueTuple 实例，该方法将抛出*参数异常*。

**例 1:**

```cs
// C# program to illustrate the 
// concept of CompareTo method
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating value tuples with two elements
        var MyTple1 = ValueTuple.Create(56, 45);
        var MyTple2 = ValueTuple.Create(56, 3);
        var MyTple3 = ValueTuple.Create(56, 45);
        var MyTple4 = ValueTuple.Create(5345, 45);

        // Using CompareTo method
        int res1 = MyTple1.CompareTo(MyTple2);
        int res2 = MyTple1.CompareTo(MyTple3);
        int res3 = MyTple1.CompareTo(MyTple4);

        // Display result
        Console.WriteLine("Result 1: " + res1);
        Console.WriteLine("Result 2: " + res2);
        Console.WriteLine("Result 3: " + res3);
    }
}
```

**Output:**

```cs
Result 1: 1
Result 2: 0
Result 3: -1

```

**例 2:**

```cs
// C# program to illustrate the
// use of CompareTo method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating value tuples with one element
        var MyVTple1 = ValueTuple.Create(2018);
        var MyVTple2 = ValueTuple.Create(2018);

        // Compare both value tuples
        // Using CompareTo method
        if (MyVTple1.CompareTo(MyVTple2) == 0) 
        {
            Console.WriteLine("Welcome to GeeksforGeeks");
        }

        else 
        {
            Console.WriteLine("Page Not Found");
        }
    }
}
```

**Output:**

```cs
Welcome to GeeksforGeeks

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . value tuple . compare to？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple.compareto?view=netframework-4.8)