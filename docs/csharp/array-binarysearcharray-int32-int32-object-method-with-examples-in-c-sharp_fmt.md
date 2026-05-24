# Array.BinarySearch(Array, Int32, Int32, Object) 方法，用 C# 举例

> 原文：[https://www.geeksforgeeks.org/array-binarysearcharray-int32-int32-object-method-with-examples-in-c-sharp/](https://www.geeksforgeeks.org/array-binarysearcharray-int32-int32-object-method-with-examples-in-c-sharp/)

`Array.BinarySearch(Array, Int32, Int32, Object)` 方法用于在一维排序数组中的一系列元素中搜索一个值，使用由数组的每个元素和指定的值实现的 `IComparable` 接口。它只在用户定义的指定边界内搜索。

## 语法

```cs
public static int BinarySearch(Array array, int index, int length, object value);
```

## 参数

*   `array`：是一维数组，我们要在其中搜索一个元素。
*   `index`：是要开始搜索的范围的起始索引。
*   `length`：是我们要搜索的范围的长度。
*   `value`：是我们要搜索的值。

## 返回值

如果找到 `value`，则返回指定的 `array` 中指定的 `value` 的索引，否则返回负数。返回值有如下几种不同的情况：

*   如果在 `array` 中没有找到 `value` 并且 `value` 小于一个或多个元素，则返回的负数是大于 `value` 的第一个元素的索引的按位补码。
*   如果找不到 `value` 并且 `value` 大于数组中的所有元素，则返回的负数是（最后一个元素的索引加 1）的按位补数。
*   如果使用非排序数组调用此方法，返回值可能不正确，并且可能返回负数，即使数组中存在 `value`。

## 异常

*   `ArgumentNullException`：如果 `array` 为空。
*   `RankException`：如果 `array` 是多维的。
*   `ArgumentOutOfRangeException`：如果 `index` 小于 `array` 的下限 **或** `length` 小于 0。
*   `ArgumentException`：如果 `index` 和 `length` 没有在 `array` 中指定有效范围 **或** `value` 的类型与 `array` 的元素不兼容。
*   `InvalidOperationException`：如果 `value` 未实现 `IComparable` 接口，并且搜索遇到未实现 `IComparable` 接口的元素。

以下程序说明了上述方法：

### 示例 1

```cs
// C# Program to illustrate the use of 
// Array.BinarySearch(Array, Int32, 
// Int32, Object) Method
using System;
using System.IO;

class GFG {

    // Main Method
    static void Main()
    {
        // initializing the integer array
        int[] intArr = {42, 5, 7, 12, 56, 1, 32};

        // sorts the intArray as it must be 
        // sorted before using method
        Array.Sort(intArr);

        // printing the sorted array
        foreach(int i in intArr) Console.Write(i + " "
                                              + "\n");

        // intArr is the array we want to find
        // and 1 is the starting index
        // of the range to search. 5 is the 
        // length of the range to search.
        // 32 is the object to search
        int index = Array.BinarySearch(intArr, 1, 5, 32);

        if (index >= 0) {

            // if the element is found it 
            // returns the index of the element
            Console.Write("Index: " + index);
        }

        else {

            // if the element is not
            // present in the array or
            // if it is not in the 
            // specified range it prints this
            Console.Write("Element is not found");
        }
    }
}
```

**输出：**

```cs
Index: 4
```

### 示例 2

如果元素不在数组中，它会打印一个负值，或者它超出了范围。

```cs
// C# Program to illustrate the use of 
// Array.BinarySearch(Array, Int32, 
// Int32, Object) Method
using System;
using System.IO;

class GFG {

    // Main Method
    static void Main()
    {
        // initializing the integer array
        int[] intArr = {42, 5, 7, 12,
                        56, 1, 32};

        // sorts the intArray as it must be 
        // sorted before using Method
        Array.Sort(intArr);

        // printing the sorted array
        foreach(int i in intArr) Console.Write(i + " "
                                              + "\n");

        // intArr is the array we want to
        // find. and 1 is the starting
        // index of the range to search. 5 is 
        // the length of the range to search
        // 44 is the object to search
        int index = Array.BinarySearch(intArr, 1, 5, 44);

        // as the element is not present
        // it prints a negative value.
        Console.Write("Index :" + index);
    }
}
```

**输出：**

```cs
Index :-7
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.array.binarysearch?view=netframework-4.7.2#System_Array_BinarySearch_System_Array_System_Int32_System_Int32_System_Object_](https://docs.microsoft.com/en-us/dotnet/api/system.array.binarysearch?view=netframework-4.7.2#System_Array_BinarySearch_System_Array_System_Int32_System_Int32_System_Object_)