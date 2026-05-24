# 如何在 C# 中对数组进行排序：Array.Sort() 方法集 - 1

> 原文：[https://www.geeksforgeeks.org/how-to-sort-an-array-in-c-sharp-array-sort-method-set-1/](https://www.geeksforgeeks.org/how-to-sort-an-array-in-c-sharp-array-sort-method-set-1/)

`Array.Sort` 方法用于对一维数组中的元素进行排序。此方法的重载列表中有 17 种方法，如下所示：

*   [`Sort<T>(T[])` 方法](#m1)
*   [`Sort<T>(T[], IComparer<T>)` 方法](#m2)
*   [`Sort<T>(T[], Int32, Int32)` 方法](#m3)
*   [`Sort<T>(T[], Comparison<T>)` 方法](#m4)
*   `Sort(Array, Int32, Int32, IComparer)` 方法
*   `Sort(Array, Array, Int32, Int32, IComparer)` 方法
*   `Sort(Array, Int32, Int32)` 方法
*   `Sort(Array, Array, Int32, Int32)` 方法
*   `Sort(Array, IComparer)` 方法
*   `Sort(Array, Array, IComparer)` 方法
*   `Sort(Array, Array)` 方法
*   `Sort(Array)` 方法
*   `Sort<T>(T[], Int32, Int32, IComparer<T>)` 方法
*   `Sort<TKey>(TKey[], TValue[])` 方法
*   `Sort<TKey>(TKey[], TValue[], IComparer<TKey>)` 方法
*   `Sort<TKey>(TKey[], TValue[], Int32, Int32)` 方法
*   `Sort<TKey,TValue>(TKey[], TValue[], Int32, Int32, IComparer<TKey>)` 方法

这里我们将讨论前 4 种方法。

### `Sort<T>(T[])` 方法

该方法使用数组中每个元素的 `IComparable<T>` 泛型接口实现对数组中的元素进行排序。

> **语法：** `public static void Sort<T>(T[] array);`
>
> **参数：**
> `array`：要排序的一维零基数组。

**异常：**

*   `ArgumentNullException`：如果 `array` 为 `null`。
*   `InvalidOperationException`：如果数组中的一个或多个元素没有实现 `IComparable<T>` 泛型接口。

**示例：**

```cs
// C# Program to illustrate the use 
// of the Array.Sort<T>(T[]) Method
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    public static void Main()
    {
        // array elements
        string[] arr = new string[5] { "A", "D", "X", "G", "M" };

        foreach(string g in arr)
        {
            Console.WriteLine(g);
            // display original array
        }

        Console.WriteLine("\nAfter Sort:");
        Array.Sort(arr);

        foreach(string g in arr)
        {
            Console.WriteLine(g);
            // display sorted array
        }

        Console.WriteLine("\nB sorts between :");

        // binary Search for "B"
        int index = Array.BinarySearch(arr, "B");

        // call "sortT" function
        // which is the Sort<T>(T[]) function
        sortT(arr, index);

        Console.WriteLine("\nF sorts between :");
        index = Array.BinarySearch(arr, "F");
        sortT(arr, index);
    }

    public static void sortT<T>(T[] arr, int index)
    {
        // If the index is negative, 
        // it represents the bitwise
        // complement of the next larger 
        // element in the array.
        if (index < 0) {
            index = ~index;

            if (index == 0)
                Console.Write("beginning of array");
            else
                Console.Write("{0} and ", arr[index - 1]);

            if (index == arr.Length)
                Console.WriteLine("end of array.");
            else
                Console.WriteLine("{0}", arr[index]);
        }
    }
}
```

**输出：**

```cs
A
D
X
G
M

After Sort:
A
D
G
M
X

B sorts between :
A and D

F sorts between :
D and G
```

### `Sort<T>(T[], IComparer<T>)` 方法

该方法使用指定的 `IComparer<T>` 泛型接口对数组中的元素进行排序。

> **语法：** `public static void Sort<T>(T[] array, System.Collections.Generic.IComparer<T> comparer);`
>
> **参数：**
> *   `T`：是数组元素的类型。
> *   `array`：是要排序的一维数组。
> *   `comparer`：比较元素时使用的 `IComparer<T>` 泛型接口实现，如果为 `null`，则使用每个元素的 `IComparable<T>` 泛型接口实现。

**异常：**

*   `ArgumentNullException`：如果 `array` 为 `null`。
*   `InvalidOperationException`：如果 `comparer` 为 `null`，并且没有实现 `IComparable<T>` 泛型接口。
*   `ArgumentException`：如果 `comparer` 的实现导致排序时出错。

**示例：**

```cs
// C# program to demonstrate the use of the 
// Array.Sort<T>(T[], IComparer<T>) method
using System;
using System.Collections.Generic;

public class GeeK : IComparer<string> {
    public int Compare(string x, string y)
    {
        // Compare x and y in reverse order.
        return x.CompareTo(y);
    }
}

class GFG {

    // Main Method
    public static void Main()
    {
        // array elements
        string[] arr = new string[5] {"A", "D", "X", "G", "M" };

        foreach(string g in arr)
        {
```

# Array.Sort 方法示例与说明

## 完整代码示例

```cs
// display original array
Console.WriteLine(g);
}

Console.WriteLine("\nAfter Sort: ");
GeeK gg = new GeeK();

// Sort<T>(T[], IComparer<T>) method
Array.Sort(arr, gg);

foreach(string g in arr)
{
    // display sorted array
    Console.WriteLine(g);
}

Console.WriteLine("\nD Sorts between :");

// binary Search for "D"
int index = Array.BinarySearch(arr, "D");

// call "sortT" function
sortT(arr, index);

Console.WriteLine("\nF Sorts between :");
index = Array.BinarySearch(arr, "F");
sortT(arr, index);
}

public static void sortT<T>(T[]arr, int index)
{
    if (index < 0)
    {
        // If the index is negative,
        // it represents the bitwise
        // complement of the next
        // larger element in the array.
        index = ~index;

        Console.Write("Not found. Sorts between: ");

        if (index == 0)
            Console.Write("Beginning of array and ");
        else
            Console.Write("{0} and ", arr[index-1]);

        if (index == arr.Length)
            Console.WriteLine("end of array.");
        else
            Console.WriteLine("{0}.", arr[index]);
    }
    else
    {
        Console.WriteLine("Found at index {0}.", index);
    }
}
}
```

**Output:**

```cs
A
D
X
G
M

After Sort:
A
D
G
M
X

D Sorts between :
Found at index 1.

F Sorts between :
Not found. Sorts between: D and G.
```

## `Array.Sort<T>(T[], Int32, Int32)` 方法

该方法使用数组中每个元素的 `IComparable<T>` 通用接口实现对数组中的某个范围内的元素进行排序。

> **语法:** `public static void Sort<T>(T[] array, int index, int length);`
>
> **参数:**
>
> *   `array`: 是要排序的一维、从零开始的数组。
> *   `index`: 是要排序范围的起始索引。
> *   `length`: 是要排序的范围内的元素个数。

**异常:**

*   `ArgumentNullException`: 如果 `array` 为空。
*   `ArgumentOutOfRangeException`: 如果 `index` 小于数组的下限或者 `length` 小于零。
*   `ArgumentException`: 如果 `index` 和 `length` 没有在数组中指定有效的范围。
*   `InvalidOperationException`: 如果数组中的一个或多个元素没有实现 `IComparable<T>` 泛型接口。

**示例:**

```cs
// C# program to demonstrate the use of
// Array.Sort<T>(T[], Int32, Int32) method
using System;
using System.Collections.Generic;

public class Geek : IComparer<string> {
    public int Compare(string x, string y)
    {
        // Compare y and x in reverse order.
        return y.CompareTo(x);
    }
}

public class Example {
    // Main Method
    public static void Main()
    {
        // Array elements
        string[] arr = {"AB", "CD",
           "GH", "EF", "MN", "IJ"};

        Console.WriteLine("Original Array :");
        Display(arr);

        Console.WriteLine("\nSort the array between " +
                          "index 1 to 4");

        // Array.Sort(T[], Int32, Int32) method
        // sort will happen in between
        // index 1 to 4
        Array.Sort(arr, 1, 4);
        Display(arr);

        Console.WriteLine("\nSort the array reversely" +
                          " in between index 1 to 4");

        // sort will happen in between
        // index 1 to 4 reversely
        Array.Sort(arr, 1, 4, new Geek());
        Display(arr);
    }

    public static void Display(string[] arr)
    {
        foreach(string g in arr)
        {
            Console.WriteLine(g);
        }
    }
}
```

**Output:**

```cs
Original Array :
AB
CD
GH
EF
MN
IJ

Sort the array between index 1 to 4
AB
CD
EF
GH
MN
IJ

Sort the array reversely in between index 1 to 4
AB
MN
GH
EF
CD
IJ
```

## `Array.Sort<T>(T[], Comparison<T>)` 方法

此方法使用指定的 `Comparison<T>` 对数组中的元素进行排序。

> **语法:** `public static void Sort<T>(T[] array, Comparison<T> comparison);`
>
> **参数:**
>
> *   `array`: 是要排序的一维从零开始的数组。
> *   `comparison`: 是比较元素时要用到的 `Comparison<T>`。

**异常:**

*   `ArgumentNullException`: 如果 `array` 为 `null` 或者 `comparison` 为 `null`。
*   `ArgumentException`: 如果执行比较导致排序时出错。

**示例:**

```cs
// C# program to demonstrate the use of the
// Array.Sort<T>(T[ ], Comparison<T>) Method
using System;
using System.Collections.Generic;

class GFG {
    private static int CompareComp(string x, string y)
    {
        if (y == null && x == null) {
            // If x and y is null
            // then x and y are same
            return 0;
        }
        else {
            // If x is null but y is not
            // null then y is greater.
            return -1;
        }
    }

    // Main method
    public static void Main()
    {
        string[] arr = {"Java", "C++", "Scala",
                        "C", "Ruby", "Python"};

        Console.WriteLine("Original Array: ");
        // display original array
        Display(arr);

        Console.WriteLine("\nSort with Comparison: ");
        // Array.Sort<T>(T[], Comparison<T>)
        // Method
        Array.Sort(arr, CompareComp);
        // display sorted array
        Display(arr);
    }

    // Display function
    public static void Display(string[] arr)
    {
        foreach(string g in arr)
        {
            Console.WriteLine(g);
        }
    }
}
```

**Output:**

```cs
Original Array:
Java
C++
Scala
C
Ruby
Python

Sort with Comparison:
Python
Ruby
C
Scala
C++
Java
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.array.sort?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.sort?view=netframework-4.7.2)