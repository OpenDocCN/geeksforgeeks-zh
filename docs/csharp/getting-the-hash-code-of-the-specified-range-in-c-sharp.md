# 获取 C# 中指定范围的哈希码

> 原文:[https://www . geesforgeks . org/get-the-hash-code-of-the-specified-in-c-sharp/](https://www.geeksforgeeks.org/getting-the-hash-code-of-the-specified-range-in-c-sharp/)

在 C# 8.0 中引入了[范围结构](https://www.geeksforgeeks.org/range-structure-in-c-sharp-8-0/)。它表示一个有开始和结束索引的范围。您可以借助 range 结构提供的 **GetHashCode()方法**获取指定范围的哈希代码。此方法返回指定实例的哈希代码。

**语法:**

```cs
public override int GetHashCode();
```

**例 1:**

```cs
// C# program to illustrate how to find 
// the hash code of the given ranges
// Using GetHashCode() method of Range
// struct
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

        // Get the hash code of the given ranges
        Console.WriteLine("Hash Code of Range_1: " +r1.GetHashCode());
        Console.WriteLine("Hash Code of Range_2: " + r2.GetHashCode());
        Console.WriteLine("Hash Code of Range_3: " + r3.GetHashCode());
    }
}
}
```

**输出:**

```cs
Hash Code of Range_1: -1254614029
Hash Code of Range_2: 853498667
Hash Code of Range_3: -1528050329

```

**例 2:**

```cs
// C# program to illustrate how to find
// the hash code of the given ranges
// Using GetHashCode() method of Range struct
using System;

namespace range_example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Creating and initializing an array
        int[] arr = new int[8] {100, 200, 300, 400,
                               500, 600, 700, 800};

        // Creating a range
        // using StartAt() method
        var r = Range.StartAt(3);
        var new_arr = arr[r];

        // Displaying the range
        // and the elements
        Console.WriteLine("Range: " + r);
        Console.Write("HashCodes: ");

        foreach(var i in new_arr)
            Console.Write({content}quot; [{i.GetHashCode()}]");
    }
}
}
```

**输出:**

```cs
Range: 3..^0
HashCodes:  [400] [500] [600] [700] [800]

```