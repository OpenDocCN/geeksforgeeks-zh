# 在 C# 中找到指定范围的起始索引

> 原文:[https://www . geesforgeks . org/find-the-start-index-of-the-specified-in-c-sharp/](https://www.geeksforgeeks.org/finding-the-start-index-of-the-specified-range-in-c-sharp/)

在 C# 8.0 中引入了[范围结构](https://www.geeksforgeeks.org/range-structure-in-c-sharp-8-0/)。它表示具有开始和结束索引的范围。您可以借助范围结构提供的**开始属性**找到给定范围的开始索引。
**语法:**

```cs
public property Index Start { Index get(); };
```

这里，索引表示范围的包含起始索引。
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the use
// of Start property of Range struct
using System;

namespace range_example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Creating range
        // using Range Constructor
        var r1 = new Range(0, 5);

        // Creating range
        // using range operator
        Range r2 = 3..7;

        // Finding the Starting
        // index of r1 and r2 ranges
        // Using Start property
        var res1 = r1.Start;
        Console.WriteLine("Starting index of r1 range: " + res1);

        var res2 = r2.Start;
        Console.WriteLine("Starting index of r2 range: " + res2);
    }
}
}
```

**输出:**

```cs
Starting index of r1 range: 0
Starting index of r2 range: 3
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate how to use
// Start property of Range structure
using System;

namespace range_example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Creating and initializing an array
        string[] arr = new string[8] {"Archery", "Badminton", "Cricket", "Bowling",
                                   "Boxing", "Curling", "Tennis", "Skateboarding"};

        // Creating ranges
        // Using Range(Index, Index)
        // Constructor
        var r1 = new Range(0, 3);
        var r2 = new Range(4, 7);

        // Finding the start index
        // of the specified range
        // Using Start property
        var res1 = r1.Start;
        var res2 = r2.Start;
        Console.WriteLine("Start Index of Range {0} is {1}"+
               " and the item is {2}", r1, res1, arr[res1]);

        Console.WriteLine("Start Index of Range {0} is {1}"+
               " and the item is {2}", r2, res2, arr[res2]);
    }
}
}
```

**输出:**

```cs
Start Index of Range 0..3 is 0 and the item is Archery
Start Index of Range 4..7 is 4 and the item is Boxing
```