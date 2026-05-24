# 如何在 C# | Array 中对数组进行排序。排序()方法|设置–5

> 原文:[https://www . geeksforgeeks . org/如何对 c-sharp-array-sort-method-set-5/](https://www.geeksforgeeks.org/how-to-sort-an-array-in-c-sharp-array-sort-method-set-5/)

**阵列。排序方法**用于对一维数组中的元素进行排序。这个方法的重载列表中有 17 个方法。这里我们将讨论以下方法:

#### 排序 <tkey tvalue="">(TKey[]，tvvalue[]，IComparer <tkey>)方法</tkey></tkey>

该方法使用指定的**比较器，根据第一个数组中的**键**对一对数组对象进行排序；T >** 通用界面。在这两个数组中，一个包含**键**，另一个包含相应的**项**。

> **语法:**公共静态空排序< TKey，TValue > (TKey[]键，TValue[]项，IComparer 比较器)；
> 这里， **TKey** 是键数组元素的类型， **TValue** 是项目数组元素的类型。
> **参数:**
> **键:**是包含要排序的键的一维数组。
> **项:**是包含与按键中的按键对应的项的一维数组。
> **比较器:**是比较元素时使用的 **IComparer < T >** 泛型接口实现。

**例外:**

*   **ArgumentNullException:** 如果密钥为空。
*   **参数异常:**如果项目不为空，且键的下限与*项目*或*项目*的下限不匹配，且键的*长度*大于*项目*的长度。
*   **无效操作禁止:**如果*比较*为 null

**例:**

## c sharp . c sharp . c sharp . c sharp

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

#### 排序 <tkey tvalue="">(TKey[]，TValue[]，Int32，Int32)方法</tkey>

该方法用于根据第一个数组中的**键**对一对数组对象中的一系列元素进行排序。在这两个数组中，一个包含**键**，另一个包含相应的**项**。

> **语法:**公共静态 void Sort < TKey，TValue > (TKey[]键，TValue[]项，IComparer 比较器，int index，int len)；
> 这里， **TKey** 是键数组元素的类型， **TValue** 是项目数组元素的类型。
> **参数:**
> **键:**是包含要排序的键的一维数组。
> **项:**是包含与按键中的按键对应的项的一维数组。
> **比较器:**它是比较元素时要使用的 **IComparer < T >** 泛型接口实现。
> **指数:**是排序范围的起始指数。
> **len:** 是要排序的范围内的元素个数。

**例外:**

*   **ArgumentNullException:** 如果密钥为空。
*   **ArgumentOutOfRangeException:**如果索引小于**键**或**键**的下限小于零。
*   **参数异常:**如果**项**不为空且**键的下限**与**项**或**项**的下限不匹配且键的 **len** 大于项的长度或**索引**和 **len** 未在**键数组**或**项**中指定有效范围****
*   **无效操作异常:**当**键数组**中的一个或多个元素没有实现**可比较<T>T5】通用接口时。**

**例:**

## c sharp . c sharp . c sharp . c sharp

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

**Output:** 

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

#### Sort <tkey tvalue="">(TKey[]，TValue[]，Int32，Int32，icomparer】法</tkey>

此方法用于使用指定的**比较器< T >** 通用接口，基于第一个数组中的**键**对一对数组对象中的一系列元素进行排序。在这两个数组中，一个包含**键**，另一个包含相应的**项**。

> **语法:**公共静态视线输出<【tkey，tvalue】>(tkkey，TValue[] items，int index，int len，icmpar<tkey>比较)；
> 
> **参数:**
> **键:**包含要排序的键的一维数组。
> **项:**是包含与按键中的按键对应的项的一维数组。
> **比较器:**它是比较元素时要使用的 **IComparer < T >** 泛型接口实现。
> **索引:**是要排序范围的起始索引。
> **len:** 是要排序的范围内的元素个数。
> **比较器:**它是比较元素时使用的 **IComparer < T >** 泛型接口实现。

**例外:**

*   **ArgumentNullException:** 如果密钥为空。
*   **ArgumentOutOfRangeException:**如果索引小于**键**或**键**的下限小于零。

*   **参数异常:**如果**项**不为空且**键的下限**与项的下限不匹配或**项**不为空且键的 **len** 大于**项**或**索引的长度**和 **len** 未在**键数组**或**项**中指定有效范围 len 没有在**item array**中指定有效范围，或者**比较器**的实现导致排序时出错。

*   **无效操作异常:**当**键数组**中的一个或多个元素没有实现**可比较<T>T5】通用接口时。**

**例:**

## c sharp . c sharp . c sharp . c sharp

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

**Output:** 

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

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . sort？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.sort?view=netframework-4.7.2)