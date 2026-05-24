# C# |将 BitArray 中的所有位设置为指定值

> 原文:[https://www . geesforgeks . org/c-sharp-将所有比特设置为指定值/](https://www.geeksforgeeks.org/c-sharp-set-all-bits-in-the-bitarray-to-the-specified-value/)

**BitArray** 类管理一个紧凑的位值数组，这些位值被表示为布尔值，其中 true 表示该位在上是**，即 **1** ，false 表示该位在**下是**，即 **0** 。这个类包含在 ***系统中。集合*** 命名空间。
**毕泰雷。SetAll(布尔)**方法用于将 BitArray 中的所有位设置为指定值。**

**属性:**

*   BitArray 类是一个集合类，其中的容量始终与计数相同。
*   通过增加 ***长度*** 属性，元素被添加到数组中。
*   通过减少 ***长度*** 属性来删除元素。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。

**语法:**

```cs
public void SetAll (bool value);

```

这里， ***值*** 是分配给所有位的布尔值。

**注:**此方法为 O(n)运算，其中 n 为 Count。

下面的程序说明了 **BitArray 的使用。设置所有(布尔)**方法:

**例 1:**

```cs
// C# code to set all bits in the
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

        // Setting all bits to true
        myBitArr.SetAll(true);

        // Printing the values in myBitArr
        // It should display all the bits as true
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
True
True
True
True
True

```

**例 2:**

```cs
// C# code to set all bits in the
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

        // Setting all bits to false
        myBitArr.SetAll(false);

        // Printing the values in myBitArr
        // It should display all the bits as false
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
False
False
False
False

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . bitarray . setall？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.bitarray.setall?view=netframework-4.7.2)