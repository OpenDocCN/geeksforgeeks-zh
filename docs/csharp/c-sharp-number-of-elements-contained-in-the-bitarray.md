# C# |数组中包含的元素数量

> 原文:[https://www . geesforgeks . org/c-sharp-元素数量-包含在-bitarray/](https://www.geeksforgeeks.org/c-sharp-number-of-elements-contained-in-the-bitarray/)

**BitArray** 类管理一个紧凑的位值数组，这些位值被表示为布尔值，其中 true 表示该位在上是**，即 **1** ，false 表示该位在**下是**，即 **0** 。这个类包含在 ***系统中。集合*** 命名空间。
**毕泰雷。Count** 属性用于**获取数组中包含的元素数量**。**

**属性:**

*   BitArray 类是一个集合类，其中的容量始终与计数相同。
*   通过增加 ***长度*** 属性，元素被添加到数组中。
*   通过减少 ***长度*** 属性来删除元素。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。

**语法:**

```cs
public int Count { get; }

```

下面的程序说明了 *BitArray 的使用。计数属性*:

**例 1:**

```cs
// C# code to get the number of 
// elements contained in the BitArray
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a BitArray
        BitArray myBitArr = new BitArray(new byte[] { 0, 1, 0, 1 });

        // To get the number of elements
        // contained in the BitArray
        Console.WriteLine(myBitArr.Count);
    }
}
```

**Output:**

```cs
32

```

**例 2:**

```cs
// C# code to get the number of
// elements contained in the BitArray
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a BitArray
        BitArray myBitArr = new BitArray(new byte[] { 0 });

        // To get the number of elements
        // contained in the BitArray
        Console.WriteLine(myBitArr.Count);
    }
}
```

**Output:**

```cs
8

```

**注:**

*   **长度**和**计数**返回相同的值。长度可以设置为特定值，但计数是只读的。
*   检索该属性的值是一个 O(1)操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . bitarray . count？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.bitarray.count?view=netframework-4.7.2)