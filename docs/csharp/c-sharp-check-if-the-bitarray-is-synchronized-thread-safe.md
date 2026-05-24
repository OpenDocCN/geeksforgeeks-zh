# C# |检查 BitArray 是否同步(线程安全)

> 原文:[https://www . geeksforgeeks . org/c-sharp-check-if-the-bitarray-synchronized-thread-safe/](https://www.geeksforgeeks.org/c-sharp-check-if-the-bitarray-is-synchronized-thread-safe/)

**BitArray** 类管理一个紧凑的位值数组，这些位值被表示为布尔值，其中 true 表示该位在上是**，即 **1** ，false 表示该位在**下是**，即 **0** 。这个类包含在 ***系统中。集合*** 命名空间。
**毕泰雷。IsSynchronized** 属性用于获取一个值，该值指示对 BitArray 的访问是否同步(线程安全)。**

**属性:**

*   BitArray 类是一个集合类，其中的容量始终与计数相同。
*   通过增加 ***长度*** 属性，元素被添加到数组中。
*   通过减少 ***长度*** 属性来删除元素。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。

**语法:**

```cs
public bool IsSynchronized { get; }

```

**返回值:**该属性始终为 ***假*** 。

**示例:**

```cs
// C# code to check if the BitArray
// is synchronized (thread safe)
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a BitArray
        BitArray myBitArr = new BitArray(7, true);

        // The following code example shows how
        // to lock the collection using the SyncRoot
        // during the entire enumeration.
        lock(myBitArr.SyncRoot)
        {
            foreach(object item in myBitArr)
            {
                // Insert your code here.
                Console.WriteLine("GeeksforGeeks");
            }
        }
    }
}
```

**输出:**

```cs
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks
GeeksforGeeks

```

**注:**此方法为 O(1)运算。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . bitarray . is synchronized？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.bitarray.issynchronized?view=netframework-4.7.2)