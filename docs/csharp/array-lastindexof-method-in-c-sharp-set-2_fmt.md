# 阵列。C# 中方法的最后一个索引|集合–2

> 原文: [https://www.geeksforgeeks.org/array-lastindexof-method-in-c-sharp-set-2/](https://www.geeksforgeeks.org/array-lastindexof-method-in-c-sharp-set-2/)

`Array.LastIndexOf` 方法用于查找一维数组或数组的一部分中某个值的最后一次出现的索引。它从数组的最后一个元素开始搜索。它返回包含指定值的元素的索引。该方法重载列表中有 6 种方法如下:

*   `LastIndexOf(Array, Object)`
*   `LastIndexOf(Array, Object, Int32)`
*   `LastIndexOf(Array, Object, Int32, Int32)`
*   `LastIndexOf<T>(T[], T)`
*   `LastIndexOf<T>(T[], T, Int32)`
*   `LastIndexOf<T>(T[], T, Int32, Int32)`

在这里，我们将讨论最后三种方法。

## `LastIndexOf<T>(T[], T)` 方法

此方法搜索指定的对象，并返回整个一维数组中最后一个匹配项的索引。

> **语法:** `public static int LastIndexOf<T>(T[] arr, T value);`
> 这里， `T` 是数组的元素类型。
> **参数:**
> `arr`: 是一维数组。
> `value`: 是数组中要定位的对象。

**返回值:** 如果找到对象，则返回整个数组中最后一次出现的值的从零开始的索引，否则为 -1。
**异常:** 如果数组为空，这个方法会给出 `ArgumentNullException`。
**例:**

```cs
// C# program to demonstrate the
// Array.LastIndexOf<T>(T[], T)
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // array elements
        string[] arr = { "ABC",
                         "EFG",
                         "GHI",
                         "LMO",
                         "STW",
                         "XYZ",
                         "QRS" };

        Console.WriteLine("Original Array");

        foreach(string g in arr)
        {
            Console.WriteLine("Original array" + g);
        }

        // here the object is STW
        Console.WriteLine("\nThe position of STW is " +
                        Array.LastIndexOf(arr, "STW"));

    }
}
```

**Output:**

```cs
Original Array
Original arrayABC
Original arrayEFG
Original arrayGHI
Original arrayLMO
Original arraySTW
Original arrayXYZ
Original arrayQRS

The position of STW is 4
```

## `LastIndexOf<T>(T[], T, Int32)` 方法

此方法搜索指定的对象，并返回数组中从第一个元素延伸到指定索引的元素范围内最后一个匹配项的索引。

> **语法:** `public static int LastIndexOf<T>(T[] arr, T value, int start);`
> 这里， `T` 是数组的元素类型。
> **参数:**
> `arr`: 是一维数组。
> `value`: 是数组中要定位的对象。
> `start`: 是向后搜索的从零开始的索引。

**例外:**

*   `ArgumentNullException`: 如果数组为空。
*   `ArgumentOutOfRangeException`: 如果 `start` 在数组的有效索引范围之外。

**例:**

```cs
// C# program to demonstrate the
// Array.LastIndexOf<T>(T[], T, Int32)
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // array elements
        string[] arr = { "ABC",
                         "EFG",
                         "GHI",
                         "LMO",
                         "STW",
                         "XYZ",
                         "QRS" };

        Console.WriteLine("Original Array");
        foreach(string g in arr)
        {
            Console.WriteLine(g);
        }

        // Here the object is STW
        // the search starts from index 5
        Console.WriteLine("\nthe position of STW is " +
                     Array.LastIndexOf(arr, "STW", 5));

    }
}
```

**Output:**

```cs
Original Array
ABC
EFG
GHI
LMO
STW
XYZ
QRS

the position of STW is 4
```

## `LastIndexOf<T>(T[], T, Int32, Int32)` 方法

此方法搜索指定的对象，并返回数组中元素范围内最后一个匹配项的索引，该数组包含指定数量的元素，并在指定的索引处结束。

> **语法:** `public static int LastIndexOf<T>(T[] arr, T value, int start, int count);`
> **参数:**
> `arr`: 它是一维数组。
> `value`: 是数组中要定位的对象。
> `start`: 是后向搜索的从零开始的起始索引。
> `count`: 是要搜索的部分的元素个数。

**返回值:** 该方法将返回数组中元素范围内最后一次出现的值的从零开始的索引，该数组包含 `count` 中指定的元素数量，如果找到则在 `start` 处结束；否则，-1。
**例外:**

*   `ArgumentNullException`: 如果数组为空。
*   `ArgumentOutOfRangeException`: 如果 `start` 在数组有效索引的范围之外，或者 `start` 和 `count` 没有在数组中指定有效的部分。

**例:**

```cs
// C# program to demonstrate the
// Array.LastIndexOf(T[], T,
// Int32, Int32)
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // array elements
        string[] arr = { "ABC",
                         "EFG",
                         "GHI",
                         "LMO",
                         "STW",
                         "XYZ",
                         "QRS" };

        Console.WriteLine("Original Array");

        foreach(string g in arr)
        {
            Console.WriteLine(g);
        }

         // here the object is STW
        // the search starts from index 5
        // the search happens backward from
        // index 5 to another 2 index
        Console.WriteLine("\nthe position of STW is " +
                  Array.LastIndexOf(arr, "STW", 5, 2));

    }
}
```

**Output:**

```cs
Original Array
ABC
EFG
GHI
LMO
STW
XYZ
QRS

the position of STW is 4
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.array.lastindexof?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.lastindexof?view=netframework-4.7.2)