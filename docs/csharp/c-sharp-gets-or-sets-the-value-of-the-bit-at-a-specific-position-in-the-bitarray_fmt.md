# C# | 获取或设置位数组中特定位置的位的值

> 原文：[https://www.geeksforgeeks.org/c-sharp-gets-or-sets-the-value-of-the-bit-at-a-specific-position-in-the-bitarray/](https://www.geeksforgeeks.org/c-sharp-gets-or-sets-the-value-of-the-bit-at-a-specific-position-in-the-bitarray/)

`BitArray.Item[Int32]`属性用于获取或设置[位数组](https://www.geeksforgeeks.org/c-bitarray-class/)中特定位置的位的值。

## 语法

```cs
public bool this[int index] { get; set; }
```

这里，`index`是要获取或设置的值的从零开始的索引。

## 返回值

返回位置`index`位的布尔值。

## 异常

如果`index`小于零或`index`等于或大于[`Count`](https://www.geeksforgeeks.org/c-number-of-elements-contained-in-the-bitarray/)，则该属性抛出`ArgumentOutOfRangeException`。

以下程序说明了上述属性的使用：

### 例 1

```cs
// C# program to illustrate the
// BitArray.Item[Int32] Property
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

        // after using item[int32] property
        // changing the bit value of index 2
        myBitArr[2] = false;

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

## 输出

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
False
True
```

### 例 2

```cs
// C# program to illustrate the
// BitArray.Item[Int32] Property
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a BitArray myBitArr
        BitArray myBitArr = new BitArray(5);

        // Initializing all the bits in myBitArr
        myBitArr[0] = true;
        myBitArr[1] = false;
        myBitArr[2] = false;
        myBitArr[3] = false;
        myBitArr[4] = true;

        // after using item[int32] property
        // it will give run time error as
        // index is less than zero
        myBitArr[-1] = false;

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

## 运行时错误

> 未处理异常:
> System.ArgumentOutOfRangeException: 索引超出范围。必须是非负的，并且小于集合的大小。
> 参数名称: index

**注意：** 检索和设置该属性的值是一个 O(1) 操作。

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.bitarray.item?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.bitarray.item?view=netframework-4.7.2)