# 如何在 C# 中从指定的起点创建范围？

> 原文:[https://www . geeksforgeeks . org/如何从 c-sharp 中指定的起始位置创建范围/](https://www.geeksforgeeks.org/how-to-create-a-range-from-a-specified-start-in-c-sharp/)

在 C# 8.0 中引入了[范围结构](https://www.geeksforgeeks.org/range-structure-in-c-sharp-8-0/)。它表示一个有开始和结束索引的范围。在范围结构提供的 **StartAt()方法**的帮助下，您可以创建一个范围对象，从指定的起始索引开始到给定集合或序列的结尾。或者换句话说， *StartAt()方法*返回从指定的开始索引开始到给定集合或序列结束的范围。

**语法:**

```cs
public static Range StartAt(Index start);
```

这里，索引开始代表开始索引。

**例 1:**

```cs
// C# program to illustrate 
// how to create a range using
// StartAt() method of Range struct
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
        // using StartAt() method
        var r3 = Range.StartAt(4);

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
Range_3: 4..^0

```

**例 2:**

```cs
// C# program to illustrate how 
// to create a range using
// StartAt() method of Range struct
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
        // using StartAt() method
        var r = Range.StartAt(2);
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
Range: 2..^0
Numbers:  [300] [400] [500] [600] [700] [800]

```