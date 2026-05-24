# 如何在 C# 中对数组进行排序：Array.Sort() 方法

> 原文: [https://www.geeksforgeeks.org/how-to-sort-an-array-in-c-sharp-array-sort-method-set-4/](https://www.geeksforgeeks.org/how-to-sort-an-array-in-c-sharp-array-sort-method-set-4/)

`Array.Sort` 方法用于对一维数组中的元素进行排序。这个方法的重载列表中有 17 个方法。这里我们将讨论以下方法：

## Sort(Array) 方法

此方法使用数组中每个元素的 `IComparable` 实现对整个一维数组中的元素进行排序。

> **语法:** `public static void Sort(Array arr);`
> **参数:**
> **arr:** 是要排序的一维数组。

**例外:**

*   `ArgumentNullException`: 如果数组为空。
*   `RankException`: 如果数组是多维的。
*   `InvalidOperationException`: 如果数组中的一个或多个元素没有实现 `IComparable` 接口。

**例:**

```cs
// C# program to demonstrate the
// Array.Sort(Array) method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // Initialize two array.
        string[] arr = {"A", "E", "D",
                  "C", "F", "B", "G"};

        // Display original values of the array
        Console.WriteLine("The original array:");
        Display(arr);

        // Sort the array using two array
        Array.Sort(arr);

        Console.WriteLine("\n\nAfter sorting :");
        Display(arr);
    }

    // Display function
    public static void Display(string[] arr)
    {
        for (int i = 0; i < arr.Length; i++)
        {
            Console.Write(arr[i] + " ");
        }
    }
}
```

**Output:**

```cs
The original array:
A E D C F B G

After sorting :
A B C D E F G
```

## Sort<T>(T[], Int32, Int32, IComparer<T>) 方法

该方法使用指定的 `IComparer<T>` 泛型接口对数组中一系列元素中的元素进行排序。

> **语法:** `public static void Sort<T>(T[] arr, int start, int len, IComparer<T> comparer);`
> 这里 `T` 是数组的元素类型。
> **参数:**
> **arr:** 是要排序的一维数组。
> **start:** 是要排序范围的开始索引。
> **len:** 是要排序的范围内的元素个数。
> **comparer:** 它是比较元素时使用的 `IComparer<T>` 泛型接口实现。

**例外:**

*   `ArgumentNullException`: 如果数组为空。
*   `ArgumentOutOfRangeException`: 如果 `start` 索引小于数组的下限或 `len` 小于零。
*   `ArgumentException`: 如果 `start` 索引和 `len` 没有在数组中指定有效范围，或者 `comparer` 的实现导致排序过程中出错。
*   `InvalidOperationException`: 如果 `comparer` 为 null。

**例:**

```cs
// C# program to demonstrate the use of
// Sort<T>(T[], Int32, Int32, IComparer<T>)
// Method
using System;
using System.Collections.Generic;

class compare : IComparer<string> {

    public int Compare(string x, string y)
    {
        // Compare x to y
        return x.CompareTo(y);
    }
}

class GFG {

    // Main Method
    public static void Main()
    {
        // Initializing array
        String[] arr = {"A", "D", "B",
                  "E", "C", "F", "G"};

        // Instantiate the IComparer object
        compare cmp = new compare();

        // Display the original values of the array
        Console.WriteLine("The original array:");
        display(arr);

        // sorting range is index 1 to 4
        // "cmp" is the IComparer<T> object
        Array.Sort(arr, 1, 4, cmp);

        Console.WriteLine("\nAfter sorting the array using the IComparer:");
        display(arr);
    }

    // display function
    public static void display(String[] arr)
    {
        foreach(String a in arr)
            Console.WriteLine(a);
    }
}
```

**Output:**

```cs
The original array:
A
D
B
E
C
F
G

After sorting the array using the IComparer:
A
B
C
D
E
F
G
```

## Sort<TKey, TValue>(TKey[], TValue[]) 方法

该方法使用每个键的 `IComparable<T>` 泛型接口实现，基于第一个数组中的键对一对数组对象（一个包含键，另一个包含相应的项）进行排序。

> **语法:** `public static void Sort<TKey, TValue>(TKey[] keys, TValue[] items);`
> 这里，`TKey` 是键数组元素的类型，`TValue` 是项目数组元素的类型。
> **参数:**
> **keys:** 是包含要排序的键的一维数组。
> **items:** 是包含与 `keys` 中的键对应的项的一维数组。

**例外:**

*   `ArgumentNullException`: 如果 `keys` 为空。
*   `ArgumentException`: 如果 `items` 不为空且 `keys` 的下界与 `items` 的下界不匹配，或者 `keys` 的长度大于 `items` 的长度。
*   `InvalidOperationException`: 如果 `keys` 数组中的一个或多个元素没有实现 `IComparable<T>` 泛型接口。

**例:**

```cs
// C# program to demonstrate the use of
// Array.Sort<TKey, TValue>(TKey[], TValue[])
// Method
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
                   "L", "I", "N", "M"};

        String[] arr2 = {"A", "E", "D",
                   "C", "F", "B", "G"};

        // Instantiate the IComparer object
        compare g = new compare();

        // Display original values of the array
        Console.WriteLine("The original order of"+
                       " elements in the array:");

        Display(arr1, arr2);

        // Sort the array
        // "arr1" is keys array
        // "arr2" is items array
        // "g" is IComparer<T> object
        Array.Sort(arr1, arr2, g);

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

After Sorting:
H : A
I : F
J : E
K : D
L : C
M : G
N : B
```