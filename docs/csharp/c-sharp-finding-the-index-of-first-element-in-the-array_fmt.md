# C# | 查找数组中第一个元素的索引

> 原文：[https://www.geeksforgeeks.org/c-sharp-finding-the-index-of-first-element-in-the-array/](https://www.geeksforgeeks.org/c-sharp-finding-the-index-of-first-element-in-the-array/)

`GetLowerBound()` 方法用于查找数组中指定维度的第一个元素的索引。

## 语法

```cs
public int GetLowerBound (int dimension);
```

这里 `dimension` 是需要确定下界的数组的从零开始的维。

## 返回值

该方法的返回类型为 `System.Int32`。此方法返回数组中指定维度的第一个元素的索引。

## 异常

如果 `dimension` 的值小于零，或者等于或大于 `Rank`，该方法将给出 `IndexOutOfRangeException`。

## 注意

*   `GetLowerBound(0)` 返回数组第一维的起始索引，`GetLowerBound(Rank-1)` 返回数组最后一维的起始索引。
*   即使数组为空，`GetLowerBound` 方法也总是返回一个指示数组下界索引的值。
*   此方法是 O(1) 操作。

## 示例

以下程序说明了 `GetLowerBound()` 方法的使用：

### 例 1

```cs
// C# program to illustrate the GetLowerBound(Int32)
// method in 1-D array
using System;

public class GFG {

    // Main method
    static public void Main()
    {
        // 1-D Array
        int[] value = {1, 2, 3, 4, 5, 6, 7};

        // Get the index of the first element
        // in the given Array by using 
        // GetLowerBound(Int32) method
        int myvalue = value.GetLowerBound(0);

        Console.WriteLine("Index: {0}", myvalue);
    }
}
```

**输出：**

```cs
Index: 0
```

### 例 2

```cs
// C# program to illustrate the GetLowerBound(Int32)
// method when the array is empty
using System;

public class GFG {

    // Main method
    static public void Main()
    {
        // Empty 1-D Array
        int[] value = {};

        // Get the index of the first element
        // in the given Array by using 
        // GetLowerBound(Int32) method
        int myvalue = value.GetLowerBound(0);

        Console.WriteLine("Index: {0}", myvalue);
    }
}
```

**输出：**

```cs
Index: 0
```

## 参考

[https://docs.microsoft.com/en-us/dotnet/api/system.array.getlowerbound?view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.array.getlowerbound?view=netcore-2.1)