# 在 C# 中查找从开始到结束的范围的所有元素

> 原文:[https://www . geeksforgeeks . org/find-从起点到终点的所有要素-in-c-sharp/](https://www.geeksforgeeks.org/finding-all-the-elements-of-a-range-from-start-to-end-in-c-sharp/)

在 C# 8.0 中引入了[范围结构](https://www.geeksforgeeks.org/range-structure-in-c-sharp-8-0/)。它表示一个有开始和结束索引的范围。在范围结构提供的**全部属性**的帮助下，您可以找到从开始索引到结束的所有范围对象。该属性始终返回 *0..^0* 系列。
**语法:**

```cs
public static property Range All { Range get(); };
```

这里，范围代表从开始到结束的索引。
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the use of the
// All property of the Range struct
using System;

namespace range_example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Creating range
        // using Range Constructor
        var r = new Range(0, 5);

        // Getting the range objects from
        // the starting index to end
        // Using All property
        var new_r = Range.All;
        Console.WriteLine(new_r);
    }
}
}
```

**输出:**

```cs
0..^0
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate how to use
// All property of the Range struct
using System;

namespace range_example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Creating and initializing an array
        int[] arr = new int[10] {23, 45, 67, 78,
                        89, 34, 89, 43, 67, 89};

        // Finding all the range
        // Using All Property
        // of Range struct
        var value = Range.All;
        var a = arr[value];

        // Displaying range and elements
        Console.WriteLine("Range: " + value);
        Console.WriteLine("Numbers: ");

        foreach(var i in a)
            Console.Write({content}quot;{i}, ");
    }
}
}
```

**输出:**

```cs
Range: 0..^0
Numbers:
23,  45,  67,  78,  89,  34,  89,  43,  67,  89, 
```