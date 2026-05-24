# 在 C# 中找到指定范围的结束索引

> 原文:[https://www . geeksforgeeks . org/find-the-end-index-of-the-specified-in-c-sharp/](https://www.geeksforgeeks.org/finding-the-end-index-of-the-specified-range-in-c-sharp/)

在 C# 8.0 中引入了[范围结构](https://www.geeksforgeeks.org/range-structure-in-c-sharp-8-0/)。它表示一个有开始和结束索引的范围。在范围结构提供的**结束属性**的帮助下，您可以找到给定范围的结束索引。
**语法:**

```cs
public property Index End { Index get(); };
```

这里，*指标*代表结束指标。
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the use
// of End property of Range struct
using System;

namespace range_example {

class Program {

    static void Main(string[] args)
    {

        // Creating range
        // using Range Constructor
        var r1 = new Range(0, 5);

        // Creating range
        // using range operator
        Range r2 = 3..7;

        // Finding the last index
        // of r1 and r2 ranges
        // Using End property
        var res1 = r1.End;
        Console.WriteLine("End index of r1 range: " + res1);

        var res2 = r2.End;
        Console.WriteLine("End index of r2 range: " + res2);
    }
}
}
```

**输出:**

```cs
End index of r1 range: 5
End index of r2 range: 7
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate how to use
// End property of Range structure
using System;

namespace range_example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Creating and initializing an array
        string[] arr = new string[8] {"Archery", "Badminton", "Cricket",
             "Bowling", "Boxing", "Curling", "Tennis", "Skateboarding"};

        // Creating ranges
        // Using Range(Index, Index)
        // Constructor
        var r1 = new Range(0, 3);
        var r2 = new Range(4, 7);

        // Finding the last index
        // of the specified range
        // Using End property
        var res1 = r1.End;
        var res2 = r2.End;
        Console.WriteLine("End Index of Range {0} is {1}"+
             " and the item is {2}", r1, res1, arr[res1]);

        Console.WriteLine("End Index of Range {0} is {1} and"+
                     " the item is {2}", r2, res2, arr[res2]);
    }
}
}
```

**输出:**

```cs
End Index of Range 0..3 is 3 and the item is Bowling
End Index of Range 4..7 is 7 and the item is Skateboarding
```