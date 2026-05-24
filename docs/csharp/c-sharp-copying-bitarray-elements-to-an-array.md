# C# |将数组元素复制到数组中

> 原文:[https://www . geesforgeks . org/c-sharp-copy-bitarray-elements to a array/](https://www.geeksforgeeks.org/c-sharp-copying-bitarray-elements-to-an-array/)

**BitArray** 类管理一个紧凑的位值数组，这些位值被表示为布尔值，其中 true 表示该位在上是**，即 **1** ，false 表示该位在**下是**，即 **0** 。这个类包含在 ***系统中。集合*** 命名空间。
**毕泰雷。CopyTo(Array，Int32)** 方法用于将整个 BitArray **复制到兼容的一维数组中，**从目标数组的指定索引处开始。**

**属性:**

*   BitArray 类是一个集合类，其中的容量始终与计数相同。
*   通过增加 ***长度*** 属性，元素被添加到数组中。
*   通过减少 ***长度*** 属性来删除元素。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。

**语法:**

```cs
public void CopyTo (Array arr, int index);

```

**参数:**

*   **arr:** 是一维数组，是从 BitArray 复制的元素的目的地。数组必须具有从零开始的索引。
*   **索引:**是数组中从零开始复制的索引。

**异常:**

*   **参数空异常:**如果 *arr* 为空。
*   **argumentoutofrangerexception:**如果索引小于零。
*   **参数异常:**如果 *arr* 是多维的**或**源数组中的元素数量大于从索引到目标数组末尾的可用空间。
*   **InvalidCastException :** 如果源数组的类型不能自动转换为目标数组的类型。

下面给出了一些例子，以便更好地理解实现:

**例 1:**

```cs
// C# code to copy BitArray to Array,
// starting at the specified index
// of the target array
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a BitArray
        BitArray myBitArr = new BitArray(4);

        myBitArr[0] = true;
        myBitArr[1] = true;
        myBitArr[2] = true;
        myBitArr[3] = true;

        // Creating a bool array
        bool[] myBoolArr = new bool[8];

        myBoolArr[0] = false;
        myBoolArr[1] = false;

        // Copying BitArray to Array,
        // starting at the specified index
        // of the target array
        myBitArr.CopyTo(myBoolArr, 3);

        // Displaying elements in myBoolArr
        foreach(Object obj in myBoolArr)
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
True
True
True
False

```

**例 2:**

```cs
// C# code to copy BitArray to Array,
// starting at the specified index
// of the target array
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a BitArray
        BitArray myBitArr = new BitArray(3);

        myBitArr[0] = true;
        myBitArr[1] = true;
        myBitArr[2] = true;

        // Creating a bool array
        bool[] myBoolArr = new bool[8];

        myBoolArr[0] = false;
        myBoolArr[1] = false;
        myBoolArr[2] = false;

        // Copying BitArray to Array,
        // starting at the specified index
        // of the target array
        // This should raise "ArgumentOutOfRangeException"
        // as index is less than 0
        myBitArr.CopyTo(myBoolArr, -2);

        // Displaying elements in myBoolArr
        foreach(Object obj in myBoolArr)
        {
            Console.WriteLine(obj);
        }
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:要求非负数。
> 参数名称:索引

**注:**

*   指定的数组必须是兼容的类型。仅支持 *bool* 、 *int* 和 *byte* 类型的数组。
*   该方法使用**数组。复制**复制元素。
*   这个方法是一个 O(n)运算，其中 n 是 Count。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . bitarray . copy to？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.bitarray.copyto?view=netframework-4.7.2)