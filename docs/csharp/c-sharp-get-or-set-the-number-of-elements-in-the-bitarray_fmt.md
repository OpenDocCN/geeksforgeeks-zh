# C# | 获取或设置数组中的元素数量

> 原文：[https://www.geeksforgeeks.org/c-sharp-get-or-set-the-number-of-elements-in-the-bitarray/](https://www.geeksforgeeks.org/c-sharp-get-or-set-the-number-of-elements-in-the-bitarray/)

`BitArray` 类管理一个紧凑的位值数组，这些位值被表示为布尔值，其中 `true` 表示该位在上是，即 `1`，`false` 表示该位在下是，即 `0`。这个类包含在 `System.Collections` 命名空间。
`BitArray.Length` 属性用于获取或设置数组中的元素数量。

## 属性

*   `BitArray` 类是一个集合类，其中的容量始终与计数相同。
*   通过增加 `Length` 属性，元素被添加到数组中。
*   通过减少 `Length` 属性来删除元素。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。

## 语法

```cs
public int Length { get; set; }
```

**返回值：** 数组中元素的个数。

**异常：** 如果属性设置为小于零的值，该方法将给出 `ArgumentException`。

下面的程序说明了 `BitArray.Length` 属性的使用：

### 例 1

```cs
// C# code to get or set the
// number of elements in the BitArray
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a BitArray myBitArr
        BitArray myBitArr = new BitArray(new byte[] { 0, 0, 0, 1 });

        // Displaying the number of
        // elements in myBitArr
        Console.WriteLine(myBitArr.Length);
    }
}
```

**Output:**

```cs

```

### 例 2

```cs
// C# code to get or set the
// number of elements in the BitArray
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a BitArray myBitArr
        BitArray myBitArr = new BitArray(new byte[] {});

        // Displaying the number of
        // elements in myBitArr
        Console.WriteLine(myBitArr.Length);
    }
}
```

**Output:**

```cs

```

## 注

*   `Length` 和 `Count` 返回相同的值。`Length` 可以设置为特定值，但 `Count` 是只读的。
*   如果 `Length` 设置为小于 `Count` 的值，则数组将被截断，索引值 `-1` 之后的元素将被删除。
*   如果 `Length` 设置为大于 `Count` 的值，新元素将设置为 `false`。
*   检索该属性的值是一个 O(1) 操作。设置该属性是一个 O(n) 操作。

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.bitarray.length?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.bitarray.length?view=netframework-4.7.2)