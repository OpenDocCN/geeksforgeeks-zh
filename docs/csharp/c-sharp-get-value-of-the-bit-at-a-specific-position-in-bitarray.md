# C# |获取 BitArray 中特定位置的位的值

> 原文:[https://www . geeksforgeeks . org/c-sharp-在特定位置获取位值-bitarray/](https://www.geeksforgeeks.org/c-sharp-get-value-of-the-bit-at-a-specific-position-in-bitarray/)

**BitArray** 类管理一个紧凑的位值数组，这些位值被表示为布尔值，其中 true 表示该位在上是**，即 **1** ，false 表示该位在**下是**，即 **0** 。这个类包含在 ***系统中。集合*** 命名空间。
**毕泰雷。Get(Int32)** 方法用于获取 BitArray 中特定位置**的位的**值。**

**属性:**

*   BitArray 类是一个集合类，其中的容量始终与计数相同。
*   通过增加 ***长度*** 属性，元素被添加到数组中。
*   通过减少 ***长度*** 属性来删除元素。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。

**语法:**

```cs
public bool Get (int index);

```

这里，*索引*是要获取的值的从零开始的索引。

**返回值:**返回位置索引处的位的值。

**异常:**如果索引小于零或索引大于或等于数组中的元素数，该方法将给出*argumentoutofrangerexception*。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to get the value of
// the bit at a specific position
// in the BitArray
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a BitArray
        BitArray myBitArr = new BitArray(5);

        myBitArr[0] = true;
        myBitArr[1] = true;
        myBitArr[2] = false;
        myBitArr[3] = true;
        myBitArr[4] = false;

        // To get the value of index at index 2
        Console.WriteLine(myBitArr.Get(2));

        // To get the value of index at index 3
        Console.WriteLine(myBitArr.Get(3));
    }
}
```

**输出:**

```cs
False
True

```

**例 2:**

```cs
// C# code to get the value of
// the bit at a specific position
// in the BitArray
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a BitArray
        BitArray myBitArr = new BitArray(5);

        myBitArr[0] = true;
        myBitArr[1] = true;
        myBitArr[2] = false;
        myBitArr[3] = true;
        myBitArr[4] = false;

        // To get the value of index at index 6
        // This should raise "ArgumentOutOfRangeException"
        // as index is greater than or equal to
        // the number of elements in the BitArray.
        Console.WriteLine(myBitArr.Get(6));
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:索引超出范围。必须是非负的，并且小于集合的大小。
> 参数名称:索引

**例 3:**

```cs
// C# code to get the value of
// the bit at a specific position
// in the BitArray
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a BitArray
        BitArray myBitArr = new BitArray(5);

        myBitArr[0] = true;
        myBitArr[1] = true;
        myBitArr[2] = false;
        myBitArr[3] = true;
        myBitArr[4] = false;

        // To get the value of index at index -2
        // This should raise "ArgumentOutOfRangeException"
        // as index is less than zero.
        Console.WriteLine(myBitArr.Get(-2));
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:索引超出范围。必须是非负的，并且小于集合的大小。
> 参数名称:索引

**注:**此方法为 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . bitarray . get？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.bitarray.get?view=netframework-4.7.2)