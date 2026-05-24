# C# |遍历数组的枚举器

> 原文:[https://www . geeksforgeeks . org/c-sharp-enumerator-迭代通过-bitarray/](https://www.geeksforgeeks.org/c-sharp-enumerator-that-iterates-through-the-bitarray/)

**BitArray** 类管理一个紧凑的位值数组，这些位值被表示为布尔值，其中 true 表示该位在上是**，即 **1** ，false 表示该位在**下是**，即 **0** 。这个类包含在 ***系统中。集合*** 命名空间。
**毕泰雷。GetEnumerator** 方法用于**获取一个遍历 BitArray 的枚举器。****

**属性:**

*   BitArray 类是一个集合类，其中的容量始终与计数相同。
*   通过增加 ***长度*** 属性，元素被添加到数组中。
*   通过减少 ***长度*** 属性来删除元素。
*   BitArray 类提供了像 And、Or、Xor、Not 和 SetAll 这样的方法。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。

**语法:**

```cs
public System.Collections.IEnumerator GetEnumerator ();

```

**返回值:**这个方法为整个数组返回一个[表达式](https://docs.microsoft.com/en-us/dotnet/api/system.collections.ienumerator?view=netframework-4.7.2)。

下面的程序说明了 *BitArray 的使用。GetEnumerator 方法*:

**例 1:**

```cs
// C# code to return an enumerator
// that iterates through the BitArray
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a BitArray myBitArr
        // Initializing all the values to true
        BitArray myBitArr = new BitArray(5, true);

        // Function calling
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
True
True
True
True
True

```

**例 2:**

```cs
// C# code to return an enumerator
// that iterates through the BitArray
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

        // Function calling
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
False
True
True
False
True

```

**注:**

*   C# 语言的 ***foreach*** 语句隐藏了枚举器的复杂性。因此，建议使用 ***foreach*** ，而不是直接操作枚举器。
*   枚举数可用于读取集合中的数据，但不能用于修改基础集合。
*   只要集合保持不变，枚举数就保持有效。如果对集合进行了更改，例如添加、修改或删除元素，枚举数将无法恢复地失效，并且其行为未定义。
*   这个方法是一个 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . bitarray . getenumerator？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.bitarray.getenumerator?view=netframework-4.7.2)