# 如何在 C# | Array 中对数组进行排序。排序()方法集–2

> 原文:[https://www . geeksforgeeks . org/如何对 c-sharp-array-sort-method-set-2/](https://www.geeksforgeeks.org/how-to-sort-an-array-in-c-sharp-array-sort-method-set-2/)

`Array.Sort`方法用于对一维数组中的元素进行排序。这个方法的重载列表中有 17 个方法。这里我们将讨论以下方法:

*   `Sort(Array, Int32, Int32, IComparer)`方法
*   `Sort(Array, Array, Int32, Int32, IComparer)`方法
*   `Sort(Array, Int32, Int32)`方法

## `Sort(Array, Int32, Int32, IComparer)`方法

此方法使用指定的 `IComparer` 对一维数组中某个范围内的元素进行排序。

> **语法:** `public static void Sort(Array arr, int start, int len, IComparer comparer);`
>
> **参数:**
>
> `arr`: 是要排序的一维数组。
> `start`: 是排序范围的开始索引。
> `len`: 是要排序的范围内的元素个数。
> `comparer`: 比较元素时使用的是 `IComparer` 实现，使用每个元素的 `IComparable` 实现则为 `null`。

**异常:**

*   `ArgumentNullException`: 如果数组为 `null`。
*   `RankException`: 如果数组是多维的。
*   `ArgumentOutOfRangeException`: 如果 `start` 索引小于数组下限或者 `len` 小于零。
*   `ArgumentException`: 如果 `start` 索引和 `len` 没有指定数组中的有效范围，或者如果 `comparer` 的实现导致排序过程中出错。
*   `InvalidOperationException`: 如果 `comparer` 为 `null`，并且数组中的一个或多个元素没有实现 `IComparable` 接口。

**示例:**

```cs
// C# program to demonstrate the use 
// of  Array.Sort(Array, Int32, Int32, 
// IComparer) method
using System;
using System.Collections;

class comparer : IComparer {
    // Call CaseInsensitiveComparer.Compare
    public int Compare(Object x, Object y)
    {
        return (new CaseInsensitiveComparer()).Compare(x, y);
    }
}

class GFG {
    // Main Method
    public static void Main()
    {
        // initialize a array.
        string[] arr = {"ABC", "GHI", "JKL",
                        "DEF", "MNO", "XYZ"};

        // Instantiate the reverse comparer.
        IComparer g = new comparer();

        // Display original values of the array.
        Console.WriteLine("The original order of " +
                          "elements in the array:");
        Display(arr);

        // Sort a section of the array
        // using the IComparer object
        // sorting happens in the range
        // of index 1 to 4
        // "g" is IComparer object
        Array.Sort(arr, 1, 4, g);

        Console.WriteLine("\nAfter sorting in a range of" +
              " index 1 to 4 using the IComparer object:");
        Display(arr);
    }

    // Display function
    public static void Display(string[] arr)
    {
        for (int i = arr.GetLowerBound(0); 
             i <= arr.GetUpperBound(0); i++) {
            Console.WriteLine(arr[i]);
        }
    }
}
```

**Output:**

```cs
The original order of elements in the array:
ABC
GHI
JKL
DEF
MNO
XYZ

After sorting in a range of index 1 to 4 using the IComparer object:
ABC
DEF
GHI
JKL
MNO
XYZ
```

## `Sort(Array, Array, Int32, Int32, IComparer)`方法

此方法使用指定的 `IComparer`，基于第一个数组中的键对一对一维数组对象中的一系列元素进行排序。这里的对象包含键和相应的项目。

> **语法:** `public static void Sort(Array keys, Array items, int start, int len, IComparer comparer);`
>
> **参数:**
>
> `keys`: 是包含要排序的键的一维数组。
> `items`: 是一维数组，包含与 `keys` 数组中的每个键相对应的项。
> `start`: 是要排序范围的开始索引。
> `len`: 是要排序的范围内的元素个数。
> `comparer`: 比较元素时使用的是 `IComparer` 实现，使用每个元素的 `IComparable` 实现则为 `null`。

**异常:**

*   `ArgumentNullException`: 如果 `keys` 为 `null`。
*   `RankException`: 如果 `keys` 数组是多维的。
*   `ArgumentOutOfRangeException`: 如果 `start` 索引小于 `keys` 的下限或者 `len` 小于零。
*   `ArgumentException`:
    *   如果 `items` 不为 `null`，并且 `keys` 的下限与 `items` 的下限不匹配，或者
    *   如果 `items` 不为 `null`，且 `keys` 的 `length` 大于 `items` 的长度
    *   如果 `start` 索引和 `len` 没有在 `keys` 数组中指定有效范围。
    *   如果 `items` 不为 `null`，并且 `start` 索引和 `len` 没有在 `items` 数组中指定有效范围。
    *   如果 `comparer` 的实现导致排序时出错。
*   `InvalidOperationException`: 如果 `comparer` 为 `null`。

**示例:**

```cs
// C# program to demonstrate the use 
// of Array.Sort(Array, Array, Int32,
// Int32, IComparer) Method
using System;
using System.Collections;

class comparer : IComparer {
    // Call CaseInsensitiveComparer.Compare
    public int Compare(Object x, Object y)
    {
        return (new CaseInsensitiveComparer()).Compare(y, x);
    }
}

// Driver Class
class GFG {
    // Main Method
    public static void Main()
    {
        // initialize two Arrays
        String[] arr1 = {"H", "J", "K",
                    "L", "I", "N", "M"};
        String[] arr2 = {"A", "E", "D",
                    "C", "F", "B", "G"};

        // Instantiate the reverse comparer.
        IComparer g = new comparer();

        // Display original values of the array.
        Console.WriteLine("The original order of " +
                          "elements in the array:");
        Display(arr1, arr2);

        // Sort a section of the array 
        // using the IComparer object
        // sorting happens in the range
        // of index 1 to 4
        // "g" is IComparer object
        Array.Sort(arr1, arr2, 1, 4, g);

        Console.WriteLine("\nAfter sorting in a " +
                          "range of index 1 to 4 :");
        Display(arr1, arr2);
    }

    // Display function
    public static void Display(String[] arr1, String[] arr2)
    {
        for (int i = 0; i < arr1.Length; i++) 
        {
            Console.WriteLine(arr1[i] + " : " + arr2[i]);
        }
    }
}
```

**Output:**

```cs
The original order of elements in the array:
H : A
J : E
K : D
L : C
I : F
N : B
M : G

After sorting in a range of index 1 to 4 :
H : A
L : C
K : D
J : E
I : F
N : B
M : G
```

## `Sort(Array, Int32, Int32)`方法

此方法使用一维数组中每个元素的 `IComparable` 实现对数组中某个范围内的元素进行排序。

> **语法:** `public static void Sort(Array arr, int start, int len);`
>
> **参数:**
>
> `arr`: 是要排序的一维数组。
> `start`: 是要排序的区间的开始索引。
> `len`: 是要排序的范围内的元素个数。

**异常:**

*   `ArgumentNullException`: 如果数组为 `null`。
*   `RankException`: 如果数组是多维的。
*   `ArgumentOutOfRangeException`: 如果 `start` 索引小于数组下限或者 `len` 小于零。
*   `ArgumentException`: 如果 `start` 索引和 `len` 没有在数组中指定有效范围。
*   `InvalidOperationException`: 如果数组中的一个或多个元素没有实现 `IComparable` 接口。

**示例:**

```cs
// C# program to demonstrate the use of
// Array.Sort(Array, Int32, Int32) method
using System;
using System.Collections;

class GFG {
    // Main Method
    public static void Main()
    {
        // initialize a array.
        string[] arr = {"ABC", "GHI", "JKL",
                        "DEF", "MNO", "XYZ"};

        // Display original values of the array.
        Console.WriteLine("The original order of" +
                       " elements in the array:");
        Display(arr);

        // sorting happens in the
        // range of index 1 to 4
        Array.Sort(arr, 1, 4);

        Console.WriteLine("\nAfter sorting in a range of " +
               "index 1 to 4 using the IComparer object:");
        Display(arr);
    }

    // Display function
    public static void Display(string[] arr)
    {
        for (int i = arr.GetLowerBound(0); 
             i <= arr.GetUpperBound(0); i++) {
            Console.WriteLine(arr[i]);
        }
    }
}
```

**Output:**

```cs
The original order of elements in the array:
ABC
GHI
JKL
DEF
MNO
XYZ

After sorting in a range of index 1 to 4 using the IComparer object:
ABC
DEF
GHI
JKL
MNO
XYZ
```