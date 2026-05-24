# 如何在 C# 中创建一个到指定终点的范围？

> 原文:[https://www . geeksforgeeks . org/如何创建一个范围到一个指定的 c-sharp-end/](https://www.geeksforgeeks.org/how-to-create-a-range-to-a-specified-end-in-c-sharp/)

在 C# 8.0 中引入了[范围结构](https://www.geeksforgeeks.org/range-structure-in-c-sharp-8-0/)。它表示一个有开始和结束索引的范围。在范围结构提供的 **EndAt()方法**的帮助下，您可以从指定集合或序列的第一个元素到指定的结束索引创建一个范围对象。或者换句话说，EndAt()方法返回一个范围，该范围从给定集合的第一个元素开始，到指定的索引结束。

**语法:**

```cs
public static Range EndAt(Index end);
```

这里，索引结束代表结束索引。

**例 1:**

```cs
// C# program to illustrate how
// to create a range using
// EndAt() method of Range struct
using System;

namespace range_example {

class GFG {

    // Main Method 
    static void Main(string[] args)
    {
        // Creating range
        // using Range constructor
        var r1 = new Range(2, 4);

        // Creating range
        // using Range operator
        Range r2 = 1..10;

        // Creating a range
        // using EndAt() method
        var r3 = Range.EndAt(6);

        // Displaying all the ranges
        Console.WriteLine("Range_1: " + r1);
        Console.WriteLine("Range_2: " + r2);
        Console.WriteLine("Range_3: " + r3);
    }
}
}
```

**输出:**

```cs
Range_1: 2..4
Range_2: 1..10
Range_3: 0..6

```

**例 2:**

```cs
// C# program to illustrate
// how to create a range using
// EndAt() method of Range struct
using System;

namespace range_example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Creating and initializing an array
        int[] arr = new int[8] {100, 200, 300, 
                     400, 500, 600, 700, 800};

        // Creating a range
        // using EndAt() method
        var r = Range.EndAt(5);
        var new_arr = arr[r];

        // Displaying the range
        // and the elements
        Console.WriteLine("Range: " + r);
        Console.Write("Numbers: ");

        foreach(var i in new_arr)
            Console.Write({content}quot; [{i}]");
    }
}
}
```

**输出:**

```cs
Range: 0..5
Numbers:  [100] [200] [300] [400] [500]

```