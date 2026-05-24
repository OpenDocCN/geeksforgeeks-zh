# C# |将 BitArray 中特定位置的位设置为指定值

> 原文:[https://www . geeksforgeeks . org/c-sharp-将特定位置的位设置为指定值/](https://www.geeksforgeeks.org/c-sharp-set-the-bit-at-a-specific-position-in-the-bitarray-to-the-specified-value/)

**BitArray** 类管理一个紧凑的位值数组，这些位值被表示为布尔值，其中 true 表示该位在上是**，即 **1** ，false 表示该位在**下是**，即 **0** 。这个类包含在 ***系统中。集合*** 命名空间。
**毕泰雷。Set(Int32，Boolean)** 方法用于将 BitArray 中特定位置**的位设置为指定值。

**属性:**

*   BitArray 类是一个集合类，其中的容量始终与计数相同。
*   通过增加 ***长度*** 属性，元素被添加到数组中。
*   通过减少 ***长度*** 属性来删除元素。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。

**语法:**

```cs
public void Set (int index, bool value);

```

**参数:**

> **索引:**要设置的位的从零开始的索引。
> **值:**要分配给该位的布尔值。

**异常:**如果*索引*小于零**或***索引*大于或等于数组中的元素数，此方法将给出**argumentout of range 异常**。

**注:**此方法为 O(1)运算。

下面的程序说明了 *BitArray 的使用。设置(Int32，布尔)方法*:

**例 1:**

```cs
// C# code to set the bit at
// a specific position in the
// BitArray to the specified value
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a BitArray myBitArr
        // Initializing all the values to false
        BitArray myBitArr = new BitArray(5, false);

        // Printing the values in myBitArr
        // It should display all the bits as false
        Console.WriteLine("Initially the bits are as : ");

        PrintIndexAndValues(myBitArr);

        // Setting bit at index 3 to true
        myBitArr.Set(3, true);

        // Printing the values in myBitArr
        Console.WriteLine("Finally the bits are as : ");

        PrintIndexAndValues(myBitArr);
    }

    // Function to display bits
    public static void PrintIndexAndValues(IEnumerable myArr)
    {
        foreach(Object obj in myArr)
        {
            Console.WriteLine(obj);
        }
    }
}
```

**Output:**

```cs
Initially the bits are as : 
False
False
False
False
False
Finally the bits are as : 
False
False
False
True
False

```

**例 2:**

```cs
// C# code to set the bit at
// a specific position in the
// BitArray to the specified value
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a BitArray myBitArr
        BitArray myBitArr = new BitArray(5);

        // Initializing all the bits in myBitArr
        myBitArr[0] = false;
        myBitArr[1] = true;
        myBitArr[2] = true;
        myBitArr[3] = false;
        myBitArr[4] = true;

        // Printing the values in myBitArr
        Console.WriteLine("Initially the bits are as : ");

        PrintIndexAndValues(myBitArr);

        // Setting bit at index 2 to false
        myBitArr.Set(2, false);

        // Setting bit at index 3 to true
        myBitArr.Set(3, true);

        // Printing the values in myBitArr
        Console.WriteLine("Finally the bits are as : ");

        PrintIndexAndValues(myBitArr);
    }

    // Function to display bits
    public static void PrintIndexAndValues(IEnumerable myArr)
    {
        foreach(Object obj in myArr)
        {
            Console.WriteLine(obj);
        }
    }
}
```

**Output:**

```cs
Initially the bits are as : 
False
True
True
False
True
Finally the bits are as : 
False
True
False
True
True

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . bitarray . set？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.bitarray.set?view=netframework-4.7.2)