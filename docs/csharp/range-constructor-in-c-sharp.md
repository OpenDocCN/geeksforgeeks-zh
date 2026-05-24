# c# 中的范围构造器

> 原文:[https://www.geeksforgeeks.org/range-constructor-in-c-sharp/](https://www.geeksforgeeks.org/range-constructor-in-c-sharp/)

**范围(索引、指标)构造器**是[范围结构](https://www.geeksforgeeks.org/range-structure-in-c-sharp-8-0/)的一部分。此构造函数用于创建 Range 的新实例以及指定的开始和结束索引。当您使用范围运算符或构造函数创建范围时，它不会添加最后一个元素或结束索引元素。
例如，我们有一个数组{1，2，3，4，5，6 }，现在我们要打印范围[1..3]，那么它将打印 2、3。它不打印 2、3、4。
**语法:**

```cs
public Range(Index start, Index end);
```

这里，开始表示范围的起始索引，结束表示范围的最后一个索引。
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate how to
// use Range(Index, Index) constructor
using System;

namespace range_example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Creating and initializing an array
        int[] arr = new int[10] {23, 45, 67, 78,
                        89, 34, 89, 43, 67, 89};

        Index start = 2;
        Index end = 5;

        // Creating range
        // Using Range(Index,
        // Index) Constructor
        var r = new Range(start, end);
        var value = arr[r];

        // Displaying range and elements
        Console.WriteLine("Range: " + r);
        Console.Write("Numbers: ");

        foreach(var i in value)
            Console.Write({content}quot; {i}, ");
    }
}
}
```

**输出:**

```cs
Range: 2..5
Numbers:  67,  78,  89, 
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate how to
// use Range(Index, Index) constructor
using System;

namespace range_example {

class Program {

    // Main Method
    static void Main(string[] args)
    {
        // Creating and initializing an array
        string[] arr = new string[8] {"Archery", "Badminton",
                              "Cricket", "Bowling", "Boxing",
                       "Curling", "Tennis", "Skateboarding"};

        // Creating ranges
        // Using Range(Index,
        // Index) Constructor
        var r1 = new Range(0, 3);
        var r2 = new Range(4, 7);
        var value_1 = arr[r1];
        var value_2 = arr[r2];

        // Displaying range and elements
        Console.WriteLine("Range: " + r1);
        Console.Write("Sports Name: ");

        foreach(var i_1 in value_1)
            Console.Write({content}quot; {i_1} ");

        Console.WriteLine("\n\nRange: " + r2);
        Console.Write("Sports Name: ");

        foreach(var i_2 in value_2)
            Console.Write({content}quot; {i_2} ");
    }
}
}
```

**输出:**

```cs
Range: 0..3
Sports Name:  Archery  Badminton  Cricket 

Range: 4..7
Sports Name:  Boxing  Curling  Tennis 
```