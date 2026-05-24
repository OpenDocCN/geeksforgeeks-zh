# C# | 检查 BitArray 是否为只读

> 原文: [https://www.geeksforgeeks.org/c-sharp-check-if-the-bitarray-is-read-only/](https://www.geeksforgeeks.org/c-sharp-check-if-the-bitarray-is-read-only/)

## BitArray 类概述

`BitArray` 类管理一个紧凑的位值数组，这些位值被表示为布尔值，其中 `true` 表示该位在上是**，即 `1`，`false` 表示该位在**下是**，即 `0`。这个类包含在 `System.Collections` 命名空间。

## IsReadOnly 属性

`BitArray.IsReadOnly` 属性用于获取一个值，该值指示 `BitArray` 是否为只读。

### 属性特点

*   `BitArray` 类是一个集合类，其中的容量始终与计数相同。
*   通过增加 `Length` 属性，元素被添加到数组中。
*   通过减少 `Length` 属性来删除元素。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。

### 语法

```cs
public bool IsReadOnly { get; }
```

### 返回值

该属性始终为 `false`。

## 示例

```cs
// C# code to check if the
// BitArray is read-only
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {
        // Creating a BitArray
        BitArray myBitArr = new BitArray(new byte[] { 0, 0, 0, 1 });

        // Checking if the BitArray is read-only
        Console.WriteLine(myBitArr.IsReadOnly);
    }
}
```

### 输出

```cs
False
```

## 注意事项

*   只读集合在创建后不允许添加、移除或修改元素。
*   这个方法是一个 O(1) 运算。
*   只读集合只是一个带有防止修改集合的包装的集合。因此，如果对基础集合进行了更改，只读集合将反映这些更改。

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.collections.bitarray.isreadonly?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.bitarray.isreadonly?view=netframework-4.7.2)