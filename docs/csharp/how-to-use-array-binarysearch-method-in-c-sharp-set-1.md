# 如何使用数组。C# 中的 BinarySearch()方法| Set -1

> 原文:[https://www . geesforgeks . org/如何使用-数组-binary search-method-in-c-sharp-set-1/](https://www.geeksforgeeks.org/how-to-use-array-binarysearch-method-in-c-sharp-set-1/)

*阵列。BinarySearch()方法*用于在排序的[一维数组](https://www.geeksforgeeks.org/c-sharp-arrays/)中搜索一个值。该方法使用了[二分搜索法算法](https://www.geeksforgeeks.org/binary-search/)。该算法通过重复地将搜索间隔分成两半来搜索排序的数组。从覆盖整个数组的间隔开始。如果搜索关键字的值小于间隔中间的项目，请将间隔缩小到下半部分。否则，缩小到上半部分。反复检查，直到找到值或间隔为空。

**要点:**

*   在调用此方法之前，必须对数组进行排序。
*   如果数组不包含指定的值，此方法将返回负整数。
*   数组必须是一维的，否则不能使用此方法。
*   Icomparable 接口必须由数组的值或每个元素实现。
*   如果在数组中找到多个匹配的元素，方法将只返回其中一个匹配项的索引，并且索引不必是第一个匹配项的索引。

*该方法重载列表中共有 8 种方法，如下:*

*   [二元搜索(数组、对象)](https://www.geeksforgeeks.org/how-to-use-array-binarysearch-method-in-c-sharp-set-1/# 1st)
*   [二元搜索(数组、对象、比较器)](https://www.geeksforgeeks.org/how-to-use-array-binarysearch-method-in-c-sharp-set-1/# 2nd)
*   [BinarySearch(数组，Int32，Int32，Object)](https://www.geeksforgeeks.org/how-to-use-array-binarysearch-method-in-c-sharp-set-1/# 3rd)
*   [二进制搜索(数组，Int32，Int32，对象，IComparer)](https://www.geeksforgeeks.org/how-to-use-array-binarysearch-method-in-c-sharp-set-1/# 4th)
*   BinarySearch <t>(T[]，T)</t>
*   BinarySearch <t>(T[]，t，icomparer】)</t>
*   BinarySearch <t>(T[]，Int32，Int32，T)</t>
*   BinarySearch <t>(T[]、Int32、Int32、t、icomparer】</t>

#### [二进制搜索(数组、对象)方法](https://www.geeksforgeeks.org/array-binarysearcharray-object-method-with-examples-in-c/)

该方法用于在整个一维排序的[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)中搜索特定元素。它使用了由一维数组的每个元素和指定对象实现的 IComparable 接口。这个方法是一个 O(log n)操作，其中 n 是指定数组的长度。

> **语法:**公共静态 int BinarySearch (Array arr，object val)；
> **参数:**
> **arr:** 是要搜索的排序一维数组。
> **val:** 是要搜索的对象。

**返回值:**如果找到*值*，则返回指定 *arr* 中指定*值*的索引，否则返回负数。返回值有如下几种不同的情况:

*   如果未找到 *val* ，并且 *val* 小于 *arr* 中的一个或多个元素，则返回的负数是大于 *val* 的第一个元素的索引的按位补码。
*   如果未找到*值*，并且*值*大于 *arr* 中的所有元素，则返回的负数是(最后一个元素的索引加 1)的按位补数。
*   如果使用非排序数组调用此方法，返回值可能不正确，并且可能返回负数，即使 *arr* 中存在*值*。

**异常:**

*   **参数空异常:**如果 *arr* 为*空*。
*   **rankeexception:**如果 *arr* 是多维的。
*   **参数异常:**如果*值*的类型与 *arr* 的元素不兼容。
*   **invalid operationexception:**如果 *val* 没有实现 IComparable 接口，并且搜索遇到了没有实现 IComparable 接口的元素。

以下程序说明了上述方法:

**例 1:**

## C#

```cs
// C# program to illustrate the
// Array.BinarySearch(Array, Object)
// Method
using System;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        // taking an 1-D Array
        int[] arr = new int[7] { 1, 5, 7, 4, 6, 2, 3 };

        // for this method array
        // must be sorted
        Array.Sort(arr);

        Console.Write("The elements of Sorted Array: ");

        // calling the method to
        // print the values
        display(arr);

        // taking the element which is
        // to search for in a variable
        // It is not present in the array
        object s = 8;

        // calling the method containing
        // BinarySearch method
        result(arr, s);

        // taking the element which is
        // to search for in a variable
        // It is present in the array
        object s1 = 4;

        // calling the method containing
        // BinarySearch method
        result(arr, s1);
    }

    // containing BinarySearch Method
    static void result(int[] arr2, object k)
    {

        // using the method
        int res = Array.BinarySearch(arr2, k);

        if (res < 0) {
            Console.WriteLine("\nThe element to search for "
                                  + "({0}) is not found.",
                              k);
        }

        else {
            Console.WriteLine("The element to search for "
                                  + "({0}) is at index {1}.",
                              k, res);
        }
    }

    // display method
    static void display(int[] arr1)
    {

        // Displaying Elements of array
        foreach(int i in arr1)
            Console.Write(i + " ");
    }
}
```

**Output:** 

```cs
The elements of Sorted Array: 1 2 3 4 5 6 7 
The element to search for (8) is not found.
The element to search for (4) is at index 3.
```

**例 2:**

## C#

```cs
// C# program to illustrate the
// Array.BinarySearch(Array, Object)
// Method
using System;

class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        // taking an 1-D Array
        int[] arr = new int[7] { 1, 5, 7, 4, 6, 2, 3 };

        // for this method array
        // must be sorted
        Array.Sort(arr);

        Console.Write("The elements of Sorted Array: ");

        // calling the method to
        // print the values
        display(arr);

        // it will return a negative value as
        // 9 is not present in the array
        Console.WriteLine("\nIndex of 9 is: " + Array.BinarySearch(arr, 8));
    }

    // display method
    static void display(int[] arr1)
    {

        // Displaying Elements of array
        foreach(int i in arr1)
            Console.Write(i + " ");
    }
}
```

**Output:** 

```cs
The elements of Sorted Array: 1 2 3 4 5 6 7 
Index of 9 is: -8
```

#### [二进制搜索(数组、对象、比较器)方法](https://www.geeksforgeeks.org/c-array-binarysearcharray-object-icomparer-method/)

该方法用于使用指定的 IComparer 接口在整个一维排序的[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)中搜索特定元素。

> **语法:**公共静态 int BinarySearch(Array arr，Object val，IComparer comparer)
> **参数:**
> **arr** :将进行搜索的一维排序数组。
> **val** :要搜索的对象值。
> **比较器**:比较元素时，使用*比较器*实现。

**返回值:**如果找到*值*，则返回指定 *arr* 中指定*值*的索引，否则返回负数。返回值有如下几种不同的情况:

*   如果未找到 *val* ，并且 *val* 小于 *arr* 中的一个或多个元素，则返回的负数是大于 *val* 的第一个元素的索引的按位补码。
*   如果未找到*值*，并且*值*大于 *arr* 中的所有元素，则返回的负数是(最后一个元素的索引加 1)的按位补数。
*   如果使用非排序数组调用此方法，返回值可能不正确，并且可能返回负数，即使 *arr* 中存在*值*。

**异常:**

*   **参数空异常:**如果 *arr* 为空。
*   **rankeexception:**如果 *arr* 是多维的。
*   **参数异常:**如果范围小于下限*或*长度小于 0。
*   **参数异常:**如果*比较器*为空，并且值的类型与 *arr* 的元素不兼容。
*   **invalid operationexception:**如果*比较器*为空，则值不实现 IComparable 接口，并且搜索遇到不实现 IComparable 接口的元素。

**示例:**

## C#

```cs
// C# program to demonstrate the
// Array.BinarySearch(Array,
// Object, IComparer) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // initializes a new Array.
        Array arr = Array.CreateInstance(typeof(Int32), 5);

        // Array elements
        arr.SetValue(20, 0);
        arr.SetValue(10, 1);
        arr.SetValue(30, 2);
        arr.SetValue(40, 3);
        arr.SetValue(50, 4);

        Console.WriteLine("The original Array");

        // calling "display" function
        display(arr);

        Console.WriteLine("\nsorted array");

        // sorting the Array
        Array.Sort(arr);

        display(arr);

        Console.WriteLine("\n1st call");

        // search for object 10
        object obj1 = 10;

        // call the "FindObj" function
        FindObj(arr, obj1);

        Console.WriteLine("\n2nd call");
        object obj2 = 60;
        FindObj(arr, obj2);
    }

    // find object method
    public static void FindObj(Array Arr,
                               object Obj)
    {
        int index = Array.BinarySearch(Arr, Obj,
                                       StringComparer.CurrentCulture);

        if (index < 0) {
            Console.WriteLine("The object {0} is not found\nNext"
                                  + " larger object is at index {1}",
                              Obj, ~index);
        }
        else {
            Console.WriteLine("The object {0} is at index {1}",
                              Obj, index);
        }
    }

    // display method
    public static void display(Array arr)
    {
        foreach(int g in arr)
        {
            Console.WriteLine(g);
        }
    }
}
```

**Output:** 

```cs
The original Array
20
10
30
40
50

sorted array
10
20
30
40
50

1st call
The object 10 is at index 0

2nd call
The object 60 is not found
Next larger object is at index 5
```

#### [BinarySearch(数组，Int32，Int32，Object)方法](https://www.geeksforgeeks.org/array-binarysearcharray-int32-int32-object-method-with-examples-in-c-sharp/)

此方法用于在一维排序数组的元素范围内搜索值。它使用由数组的每个元素和指定值实现的 IComparable 接口。它只在用户定义的指定边界内搜索。

> **语法:**公共静态 int BinarySearch(Array arr，int i，int len，object val)；
> **参数:**
> **arr:** 这是一个一维数组，用户必须在其中搜索一个元素。
> **i:** 是用户想要开始搜索的范围的起始索引。
> **len:** 是用户想要搜索的范围长度。
> **val:** 是用户要搜索的值。

**返回值:**如果找到*值*，则返回指定 *arr* 中指定*值*的索引，否则返回负数。返回值有如下几种不同的情况:

*   如果未找到 *val* ，并且 *val* 小于 *arr* 中的一个或多个元素，则返回的负数是大于 *val* 的第一个元素的索引的按位补码。
*   如果未找到*值*，并且*值*大于 *arr* 中的所有元素，则返回的负数是(最后一个元素的索引加 1)的按位补数。
*   如果使用非排序数组调用此方法，返回值可能不正确，并且可能返回负数，即使 *arr* 中存在*值*。

**异常:**

*   **参数空异常:**如果 *arr* 为空。
*   **rankeexception:**如果 *arr* 是多维的。
*   **ArgumentOutOfRangeException:**如果索引小于数组的下界**或**长度小于 0。
*   **参数异常:**如果索引和长度没有指定数组**或**中的有效范围，则该值属于与数组元素不兼容的类型。
*   **invalidOperationException:**如果值未实现 IComparable 接口，并且搜索遇到未实现 IComparable 接口的元素。

**示例:**

## C#

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
        int[] intArr = { 42, 5, 7, 12, 56, 1, 32 };

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
            Console.WriteLine("Index of 32 is : " + index);
        }

        else {

            // if the element is not
            // present in the array or
            // if it is not in the
            // specified range it prints this
            Console.Write("Element is not found");
        }

        // intArr is the array we want to
        // find. and 1 is the starting
        // index of the range to search. 5 is
        // the length of the range to search
        // 44 is the object to search
        int index1 = Array.BinarySearch(intArr, 1, 5, 44);

        // as the element is not present
        // it prints a negative value.
        Console.WriteLine("Index of 44 is :" + index1);
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
Index of 32 is : 4
Index of 44 is :-7
```

#### [二进制搜索(数组，Int32，Int32，对象，IComparer)方法](https://www.geeksforgeeks.org/c-sharp-array-binarysearcharray-int32-int32-object-icomparer-method/)

此方法用于使用指定的 IComparer 接口在一维排序数组的元素范围内搜索值。

> **语法:**公共静态 int BinarySearch(Array arr，int index，int length，Object 值，IComparer comparer)
> **参数:**
> **arr** :待搜索的排序一维数组。
> **索引**:搜索开始范围的起始索引。
> **长度**:搜索将发生的范围的长度。
> **值**:要搜索的对象。
> **比较器**:比较元素时使用*比较器*实现。

**返回值:**返回指定 *arr* 中指定*值*的索引，如果找到*值*，则返回负数。返回值有如下几种不同的情况:

*   如果在*数组*中没有找到*值*并且*值*小于一个或多个元素，则返回的负数是大于*值*的第一个元素的索引的按位补码。
*   如果找不到*值*并且*值*大于数组中的所有元素，则返回的负数是(最后一个元素的索引加 1)的按位补数。
*   如果使用非排序数组调用此方法，返回值可能不正确，并且可能返回负数，即使数组中存在*值*。

**示例:**在本例中，我们使用“ *CreateInstance()* 方法创建一个*类型的*数组，并存储一些整数值，对数组进行排序后搜索一些值。

## C#

```cs
// C# program to demonstrate the
// Array.BinarySearch(Array,
// Int32, Int32, Object,
// IComparer) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // initializes a new Array.
        Array arr = Array.CreateInstance(typeof(Int32), 8);

        // Array elements
        arr.SetValue(20, 0);
        arr.SetValue(10, 1);
        arr.SetValue(30, 2);
        arr.SetValue(40, 3);
        arr.SetValue(50, 4);
        arr.SetValue(80, 5);
        arr.SetValue(70, 6);
        arr.SetValue(60, 7);

        Console.WriteLine("The original Array");

        // calling "display" function
        display(arr);

        Console.WriteLine("\nsorted array");

        // sorting the Array
        Array.Sort(arr);

        display(arr);

        Console.WriteLine("\n1st call");

        // search for object 10
        object obj1 = 10;

        // call the "FindObj" function
        FindObj(arr, obj1);

        Console.WriteLine("\n2nd call");
        object obj2 = 60;
        FindObj(arr, obj2);
    }

    // find object method
    public static void FindObj(Array Arr,
                               object Obj)
    {
        int index = Array.BinarySearch(Arr, 1, 4,
                                       Obj, StringComparer.CurrentCulture);

        if (index < 0) {
            Console.WriteLine("The object {0} is not found\n"
                                  + "Next larger object is at index {1}",
                              Obj, ~index);
        }
        else {
            Console.WriteLine("The object {0} is at "
                                  + "index {1}",
                              Obj, index);
        }
    }

    // display method
    public static void display(Array arr)
    {
        foreach(int g in arr)
        {
            Console.WriteLine(g);
        }
    }
}
```

**Output:** 

```cs
The original Array
20
10
30
40
50
80
70
60

sorted array
10
20
30
40
50
60
70
80

1st call
The object 10 is not found
Next larger object is at index 1

2nd call
The object 60 is not found
Next larger object is at index 5
```