# C# |反转 BitArray 中的所有位值

> 原文:[https://www . geeksforgeeks . org/c-锐-反相-所有位值-in-bitarray/](https://www.geeksforgeeks.org/c-sharp-inverting-all-bit-values-in-bitarray/)

**BitArray** 类管理一个紧凑的位值数组，这些位值被表示为布尔值，其中 true 表示该位在上是**，即 **1** ，false 表示该位在**下是**，即 **0** 。这个类包含在 ***系统中。集合*** 命名空间。
**毕泰雷。非**法**将当前 BitArray 中的所有位值**进行反相，使设置为 ***真*** 的元素变为 ***假*** ，设置为 ***假*** 的元素变为 ***真*** 。**

**属性:**

*   BitArray 类是一个集合类，其中的容量始终与计数相同。
*   通过增加 ***长度*** 属性，元素被添加到数组中。
*   通过减少 ***长度*** 属性来删除元素。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。

**语法:**

```cs
public System.Collections.BitArray Not ();

```

**返回值:**返回当前实例的反转位值。

**示例:**

```cs
// C# code to invert values in BitArray
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a BitArray
        BitArray myBitArr1 = new BitArray(4);

        // Creating a BitArray
        BitArray myBitArr2 = new BitArray(4);

        // Initializing values in myBitArr1
        myBitArr1[0] = false;
        myBitArr1[1] = false;
        myBitArr1[2] = true;
        myBitArr1[3] = true;

        // Initializing values in myBitArr2
        myBitArr2[0] = false;
        myBitArr2[1] = true;
        myBitArr2[2] = false;
        myBitArr2[3] = true;

        // Function calling to print the values
        // of BitArray myBitArr1
        Console.WriteLine("Values in BitArray myBitArr1 are : ");

        PrintValues(myBitArr1);

        // Function calling to print the values
        // of BitArray myBitArr2
        Console.WriteLine("Values in BitArray myBitArr2 are : ");

        PrintValues(myBitArr2);

        // inverting values in BitArray myBitArr1
        myBitArr1.Not();

        // inverting values in BitArray myBitArr2
        myBitArr2.Not();

        // Function calling to print the inverted values
        // of BitArray myBitArr1
        Console.WriteLine("Values in BitArray myBitArr1 are : ");

        PrintValues(myBitArr1);

        // Function calling to print the inverted values
        // of BitArray myBitArr2
        Console.WriteLine("Values in BitArray myBitArr2 are : ");

        PrintValues(myBitArr2);
    }

    // Displaying the result
    public static void PrintValues(IEnumerable myList)
    {
        foreach(Object obj in myList)
        {
            Console.WriteLine(obj);
        }
    }
}
```

**Output:**

```cs
Values in BitArray myBitArr1 are : 
False
False
True
True
Values in BitArray myBitArr2 are : 
False
True
False
True
Values in BitArray myBitArr1 are : 
True
True
False
False
Values in BitArray myBitArr2 are : 
True
False
True
False

```

**注:**此方法为 O(n)运算，其中 n 为 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . bitarray . not？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.bitarray.not?view=netframework-4.7.2)