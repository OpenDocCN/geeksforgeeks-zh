# 阵列。BinarySearch(Array，Int32，Int32，Object)方法，用 C# 举例

> 原文:[https://www . geeksforgeeks . org/array-binarysearcharay-int 32-int 32-object-method-with-examples-in-c-sharp/](https://www.geeksforgeeks.org/array-binarysearcharray-int32-int32-object-method-with-examples-in-c-sharp/)

**阵列。BinarySearch(Array，int32，int32，Object)方法**用于在一维排序数组中的一系列元素中搜索一个值，使用由数组的每个元素和指定的值实现的 IComparable 接口。它只在用户定义的指定边界内搜索。

**语法:**

```cs
public static int BinarySearch(Array array, int index, int length, object value);

```

**参数:**

*   **数组:**是一维数组，我们要在其中搜索一个元素。
*   **索引:**是要开始搜索的范围的起始索引。
*   **长度:**是我们要搜索的范围的长度。
*   **值:**是我们要搜索的值。

**返回值:**如果找到*值*，则返回指定的*数组*中指定的*值*的索引，否则返回负数。返回值有如下几种不同的情况:

*   如果在*数组*中没有找到*值*并且*值*小于一个或多个元素，则返回的负数是大于*值*的第一个元素的索引的按位补码。
*   如果找不到*值*并且*值*大于数组中的所有元素，则返回的负数是(最后一个元素的索引加 1)的按位补数。
*   如果使用非排序数组调用此方法，返回值可能不正确，并且可能返回负数，即使数组中存在*值*。

**异常:**

*   **ArgumentNullException:** 如果数组为空。
*   **rankeexception:**如果数组是多维的。
*   **argumentout of range exception:**如果范围小于下限**或**长度小于 0。
*   **参数异常:**如果*索引*和*长度*没有在*数组* **或** *值中指定有效范围*的类型与*数组*的元素不兼容。
*   **invalidOperationException:**如果值未实现 IComparable 接口，并且搜索遇到未实现 IComparable 接口的元素。

以下程序说明了上述方法:

**例 1:**

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

**Output:**

```cs
1 
5 
7 
12 
32 
42 
56 
Index: 4

```

**示例 2:** 如果元素不在数组中，它会打印一个负值，或者它超出了范围。

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

**Output:**

```cs
1 
5 
7 
12 
32 
42 
56 
Index :-7

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . binary search？view = net framework-4 . 7 . 2 # System _ Array _ binary search _ System _ Array _ System _ int 32 _ System _ int 32 _ System _ Object _](https://docs.microsoft.com/en-us/dotnet/api/system.array.binarysearch?view=netframework-4.7.2# System_Array_BinarySearch_System_Array_System_Int32_System_Int32_System_Object_)