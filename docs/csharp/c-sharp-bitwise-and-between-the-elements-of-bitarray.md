# c# | BitArray 元素之间的按位 AND

> 原文:[https://www . geeksforgeeks . org/c-sharp-bitarray 的元素间按位运算/](https://www.geeksforgeeks.org/c-sharp-bitwise-and-between-the-elements-of-bitarray/)

**BitArray** 类管理一个紧凑的位值数组，这些位值被表示为布尔值，其中 true 表示该位在上是**，即 **1** ，false 表示该位在**下是**，即 **0** 。这个类包含在 ***系统中。集合*** 命名空间。
**毕泰雷。And(BitArray)** 方法用于执行当前 BitArray 对象的元素与指定数组中对应元素之间的按位 And 运算。
当前 BitArray 对象将被修改以存储按位“与”运算的结果。**

**属性:**

*   BitArray 类是一个集合类，其中的容量始终与计数相同。
*   通过增加 ***长度*** 属性，元素被添加到数组中。
*   通过减少 ***长度*** 属性来删除元素。
*   BitArray 类提供了像 And、Or、Xor、Not 和 SetAll 这样的方法。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。

**语法:**

```cs
public System.Collections.BitArray And (System.Collections.BitArray value);

```

这里，*值*是执行按位“与”运算的数组。

**返回值:**它返回一个包含按位“与”运算结果的数组，该数组是对当前 BitArray 对象的引用。

**异常:**

*   **ArgumentNullException :** 如果值为空。
*   **ArgumentException :** 如果值和当前 BitArray 的元素数量不相同。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to do bitwise
// AND between BitArray
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
        myBitArr2[2] = false;
        myBitArr2[1] = true;
        myBitArr2[3] = true;

        // function calling
        PrintValues(myBitArr1.And(myBitArr2));
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

**输出:**

```cs
False
False
False
True

```

**例 2:**

```cs
// C# code to do bitwise
// AND between BitArray
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a BitArray
        BitArray myBitArr1 = new BitArray(4);

        // Creating a BitArray
        BitArray myBitArr2 = new BitArray(6);

        // Initializing values in myBitArr1
        myBitArr1[0] = false;
        myBitArr1[1] = false;
        myBitArr1[2] = true;
        myBitArr1[3] = true;

        // Initializing values in myBitArr2
        myBitArr2[0] = false;
        myBitArr2[2] = false;
        myBitArr2[1] = true;
        myBitArr2[3] = true;
        myBitArr2[4] = true;
        myBitArr2[5] = true;

        // function calling
        // This should raise "ArgumentException"
        // as array lengths are not same
        PrintValues(myBitArr1.And(myBitArr2));
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

**运行时错误:**

> 未处理异常:
> 系统。参数异常:数组长度必须相同。

**注:**

*   如果两个操作数都是*真*，则按位“与”运算返回*真*，如果一个或两个操作数都是*假，则返回*假*。*
*   这个方法是一个 O(n)运算，其中 n 是 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . bitarray . and？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.bitarray.and?view=netframework-4.7.2)