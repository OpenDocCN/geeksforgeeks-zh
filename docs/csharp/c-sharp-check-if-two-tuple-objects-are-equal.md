# C# |检查两个元组对象是否相等

> 原文:[https://www . geeksforgeeks . org/c-sharp-check-if-two-tuple-objects-equal/](https://www.geeksforgeeks.org/c-sharp-check-if-two-tuple-objects-are-equal/)

[元组](https://www.geeksforgeeks.org/c-sharp-tuple/)是一种数据结构，它为您提供了表示数据集的最简单方法。您也可以使用**等于方法**检查给定的元组对象是否等于指定的对象。如果给定的元组对象等于指定的对象，此方法将返回 true，否则返回 false。

**语法:**

```cs
public override bool Equals (object obj);
```

这里， *obj* 是与这个实例进行比较的对象。

**返回类型:**该方法的返回类型为*布尔*。意味着如果元组对象等于给定对象，它将返回*真*。否则，返回*假*。

**重要提示:**当满足以下条件时，该*对象*参数被视为相等:

*   如果是元组<>对象。这里的元组<>可以是 1 元组、2 元组、3 元组、4 元组、5 元组、6 元组、7 元组或 8 元组。
*   它必须包含与当前实例相同类型的相同数量的元素。
*   它的元素(包括它的嵌套组件)等于当前实例的元素。相等由每个元素的默认相等比较器确定。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to illustrate the 
// Equals method
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Taking tuple variables
        var t1 = Tuple.Create(12, 34, 56, 78);
        var t2 = Tuple.Create(12, 34, 67, 89);
        var t3 = Tuple.Create(12, 34, 56, 78);
        var t4 = Tuple.Create(34, 56, 78);

        // Check whether the given 
        // tuples are Equal or not
        // Using Equals() method
        Console.WriteLine(t1.Equals(t2));
        Console.WriteLine(t1.Equals(t3));
        Console.WriteLine(t1.Equals(t4));
    }
}
```

**Output:**

```cs
False
True
False

```

**例 2:**

```cs
// C# program to illustrate Equals
// method with nested tuple
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // Taking Tuples
        var t1 = Tuple.Create(34, 56, 78, Tuple.Create(12, 34, 56, 78));
        var t2 = Tuple.Create(12, 34, 67, 89);
        var t3 = Tuple.Create(12, 34, 56, Tuple.Create(23, 56));
        var t4 = Tuple.Create(34, 56, 78, Tuple.Create(12, 34, 56, 78));
        var t5 = Tuple.Create(12, 34, 56, Tuple.Create(24, 56));

        // Check whether the given 
        // tuples are Equal or not
        // Using Equals() method
        Console.WriteLine(t1.Equals(t2));
        Console.WriteLine(t1.Equals(t3));
        Console.WriteLine(t1.Equals(t4));
        Console.WriteLine(t3.Equals(t5));
        Console.WriteLine(t1.Equals(t5));
    }
}
```

**Output:**

```cs
False
False
True
False
False

```