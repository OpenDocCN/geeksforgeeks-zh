# 如何在 C# 中对数组进行排序：Array.Sort 方法（系列5）

> 原文：[https://www.geeksforgeeks.org/how-to-sort-an-array-in-c-sharp-array-sort-method-set-5/](https://www.geeksforgeeks.org/how-to-sort-an-array-in-c-sharp-array-sort-method-set-5/)

`Array.Sort` 方法用于对一维数组中的元素进行排序。这个方法的重载列表中有 17 个方法。这里我们将讨论以下方法：

## Sort<TKey, TValue>(TKey[], TValue[], IComparer<TKey>) 方法

该方法使用指定的比较器，根据第一个数组中的键对一对数组对象进行排序；使用 `IComparer<T>` 泛型接口。在这两个数组中，一个包含键，另一个包含相应的项。

> **语法：**
> `public static void Sort<TKey, TValue>(TKey[] keys, TValue[] items, IComparer<TKey> comparer);`
> 这里，`TKey` 是键数组元素的类型，`TValue` 是项数组元素的类型。
> **参数：**
> - `keys`：是包含要排序的键的一维数组。
> - `items`：是包含与键数组中的键对应的项的一维数组。
> - `comparer`：是比较元素时使用的 `IComparer<T>` 泛型接口实现。

**例外：**

- `ArgumentNullException`：如果 `keys` 为 `null`。
- `ArgumentException`：如果 `items` 不为 `null`，且 `keys` 的下限与 `items` 的下限不匹配，且 `keys` 的长度大于 `items` 的长度。
- `InvalidOperationException`：如果 `comparer` 为 `null`。

**例：**

```cs
// C# program to demonstrate the use of
// Array.Sort<TKey, TValue>(TKey[],
// TValue[], IComparer<TKey>) Method
using System;
using System.Collections.Generic;

class compare : IComparer<string> {

    public int Compare(string x, string y)
    {
        // Compare x to y
        return x.CompareTo(y);
    }
}

// Driver Class
class GFG {

    // Main Method
    public static void Main()
    {
        // Initialize two array
        String[] arr1 = { "H", "J", "K",
                   "L", "I", "N", "M" };

        String[] arr2 = { "A", "E", "D",
                   "C", "F", "B", "G" };

        // Instantiate the IComparer object
        compare g = new compare();

        // Display original values of the array
        Console.WriteLine("The original order of"
                    + " elements in the array:");

        Display(arr1, arr2);

        // Sort the array
        // "arr1" is keys array
        // "arr2" is items array
        // "g" is IComparer<TKey> object
        Array.Sort(arr1, arr2, g);

        Console.WriteLine("\nAfter Sorting: ");
        Display(arr1, arr2);
    }

    // Display function
    public static void Display(String[] arr1,
                               String[] arr2)
    {
        for (int i = 0; i < arr1.Length; i++)
        {
            Console.WriteLine(arr1[i] + " : " + arr2[i]);
        }
    }
}
```

**Output：**

```cs
The original order of elements in the array:
H : A
J : E
K : D
L : C
I : F
N : B
M : G

After Sorting: 
H : A
I : F
J : E
K : D
L : C
M : G
N : B
```

## Sort<TKey, TValue>(TKey[], TValue[], Int32, Int32) 方法

该方法用于根据第一个数组中的键对一对数组对象中的一系列元素进行排序。在这两个数组中，一个包含键，另一个包含相应的项。

> **语法：**
> `public static void Sort<TKey, TValue>(TKey[] keys, TValue[] items, int index, int length);`
> 这里，`TKey` 是键数组元素的类型，`TValue` 是项数组元素的类型。
> **参数：**
> - `keys`：是包含要排序的键的一维数组。
> - `items`：是包含与键数组中的键对应的项的一维数组。
> - `index`：是排序范围的起始索引。
> - `length`：是要排序的范围内的元素个数。

**例外：**

- `ArgumentNullException`：如果 `keys` 为 `null`。
- `ArgumentOutOfRangeException`：如果 `index` 小于 `keys` 或 `items` 的下限，或小于零。
- `ArgumentException`：如果 `items` 不为 `null` 且 `keys` 的下限与 `items` 的下限不匹配，且 `keys` 的 `length` 大于 `items` 的长度，或 `index` 和 `length` 未在 `keys` 数组或 `items` 中指定有效范围。
- `InvalidOperationException`：当 `keys` 数组中的一个或多个元素没有实现 `IComparable<T>` 泛型接口时。

**例：**

```cs
// C# program to demonstrate the use of
// Array.Sort<TKey, TValue>(TKey[], TValue[],
// Int32, Int32) Method
using System;

// Driver Class
class GFG {

    // Main Method
    public static void Main()
    {
        // Initialize two array
        String[] arr1 = {"H", "J", "K",
                   "L", "I", "M", "N"};

        String[] arr2 = {"A", "E", "D",
                   "C", "F", "B", "G"};

        // Display original values of the array
        Console.WriteLine("The original order of"
                    + " elements in the array:");

        Display(arr1, arr2);

        // Sort the array
        // "arr1" is keys array
        // "arr2" is items array
        // start index 1
        // rang upto index 5
        Array.Sort(arr1, arr2, 1, 5);

        Console.WriteLine("\nAfter Sorting: ");
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

**Output：**

```cs
The original order of elements in the array:
H : A
J : E
K : D
L : C
I : F
M : B
N : G

After Sorting: 
H : A
I : F
J : E
K : D
L : C
M : B
N : G
```

## Sort<TKey, TValue>(TKey[], TValue[], Int32, Int32, IComparer<TKey>) 方法

此方法用于使用指定的 `IComparer<T>` 泛型接口，基于第一个数组中的键对一对数组对象中的一系列元素进行排序。在这两个数组中，一个包含键，另一个包含相应的项。

> **语法：**
> `public static void Sort<TKey, TValue>(TKey[] keys, TValue[] items, int index, int length, IComparer<TKey> comparer);`
> **参数：**
> - `keys`：包含要排序的键的一维数组。
> - `items`：是包含与键数组中的键对应的项的一维数组。
> - `index`：是要排序范围的起始索引。
> - `length`：是要排序的范围内的元素个数。
> - `comparer`：它是比较元素时使用的 `IComparer<T>` 泛型接口实现。

**例外：**

- `ArgumentNullException`：如果 `keys` 为 `null`。
- `ArgumentOutOfRangeException`：如果 `index` 小于 `keys` 或 `items` 的下限，或小于零。
- `ArgumentException`：如果 `items` 不为 `null` 且 `keys` 的下限与 `items` 的下限不匹配，或 `items` 不为 `null` 且 `keys` 的 `length` 大于 `items` 的长度，或 `index` 和 `length` 未在 `keys` 数组或 `items` 中指定有效范围，或者 `comparer` 的实现导致排序时出错。
- `InvalidOperationException`：当 `keys` 数组中的一个或多个元素没有实现 `IComparable<T>` 泛型接口时。

**例：**

```cs
// C# program to demonstrate the use of
// Array.Sort<TKey, TValue>(TKey[], TValue[],
// Int32, Int32, IComparer<TKey>) Method
using System;
using System.Collections.Generic;

class compare : IComparer<string> {

    public int Compare(string x, string y)
    {
        // Compare x to y
        return x.CompareTo(y);
    }
}

// Driver Class
class GFG {

    // Main Method
    public static void Main()
    {
        // Initialize two array
        String[] arr1 = {"H", "J", "K",
                   "L", "I", "M", "N"};

        String[] arr2 = {"A", "E", "D",
                   "C", "F", "B", "G"};

        // Instantiate the IComparer object
        compare g = new compare();

        // Display original values of the array
        Console.WriteLine("The original order of"
                    + " elements in the array:");

        Display(arr1, arr2);

        // Sort the array
        // "arr1" is keys array
        // "arr2" is items array
        // "g" is IComparer<TKey> object
        // start index 1
        // rang upto index 5
        Array.Sort(arr1, arr2, 1, 5, g);

        Console.WriteLine("\nAfter Sorting: ");
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

**Output：**

```cs
The original order of elements in the array:
H : A
J : E
K : D
L : C
I : F
M : B
N : G

After Sorting: 
H : A
I : F
J : E
K : D
L : C
M : B
N : G
```

**参考：**

- [https://docs.microsoft.com/en-us/dotnet/api/system.array.sort?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.sort?view=netframework-4.7.2)