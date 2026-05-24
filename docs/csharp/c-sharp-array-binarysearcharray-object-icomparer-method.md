# C# |数组。二进制搜索(数组、对象、比较器)方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-array-binarysearcharray-object-I comparer-method/](https://www.geeksforgeeks.org/c-sharp-array-binarysearcharray-object-icomparer-method/)

此方法使用指定的 *IComparer* 接口在一维排序数组中搜索值。

**语法:**

```cs
public static int BinarySearch(Array arr, Object val, IComparer comparer)
```

**参数:**

*   **arr** :将进行搜索的一维排序数组。
*   **值**:要搜索的对象值。
*   **比较器**:当比较元素时，使用*比较器*实现。

**返回值:**如果找到*值*，则返回指定的*数组*中指定的*值*的索引，否则返回负数。返回值有如下几种不同的情况:

*   如果在*数组*中没有找到*值*并且*值*小于一个或多个元素，则返回的负数是大于*值*的第一个元素的索引的按位补码。
*   如果找不到*值*并且*值*大于数组中的所有元素，则返回的负数是(最后一个元素的索引加 1)的按位补数。
*   如果使用非排序数组调用此方法，返回值可能不正确，并且可能返回负数，即使数组中存在*值*。

**异常:**

*   **参数空异常:**如果*数组*为空。
*   **rankeexception:**如果*阵*是多维的。
*   **参数异常:**如果范围小于下限*或*长度小于 0。
*   **参数异常:**如果*比较器*为空，并且值的类型与*数组*的元素不兼容。
*   **invalid operationexception:**如果*比较器*为空，则值不实现 IComparable 接口，并且搜索遇到不实现 IComparable 接口的元素。

**示例 1:** 在本例中，数组存储了一些字符串值，并在对数组进行排序后找到一些字符串值。

```cs
// C# program to demonstrate the 
// Array.BinarySearch(Array, 
// Object, IComparer) Method
using System;

class GFG {

// Main Method
public static void Main()
{
    // initializes a new Array
    string[] arr = new string[5] { "ABCD", 
           "IJKL", "XYZ", "EFGH", "MNOP"};

    Console.WriteLine("The original Array");

    // calling "display" function
    display(arr);

    Console.WriteLine("\nsorted array");

    // sorting the Array
    Array.Sort(arr);
    display(arr);

    Console.WriteLine("\n1st call");

    // search for object "EFGH"
    object obj1 = "EFGH";

    // call the "FindObj" function
    FindObj(arr, obj1);

    Console.WriteLine("\n2nd call");
    object obj2 = "ABCD";
    FindObj(arr, obj2);
}

// find object method
public static void FindObj(string[] Arr,
                             object Obj)
{
    int index = Array.BinarySearch(Arr, Obj, 
             StringComparer.CurrentCulture);

    if (index < 0) 
    {
        Console.WriteLine("The object {0} is not "+
                 "found\nNext larger object is at"+
                        " index {1}", Obj, ~index);
    }

    else
    {
        Console.WriteLine("The object {0} is at "+
                         "index {1}", Obj, index);
    }
}

// display method
public static void display(string[] arr)
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
The original Array
ABCD
IJKL
XYZ
EFGH
MNOP

sorted array
ABCD
EFGH
IJKL
MNOP
XYZ

1st call
The object EFGH is at index 1

2nd call
The object ABCD is at index 0

```

**例 2:**

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

    if (index < 0) 
    {
        Console.WriteLine("The object {0} is not found\nNext"+
               " larger object is at index {1}", Obj, ~index);
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

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . binary search？view = net framework-4 . 7 . 2 # System _ Array _ binary search _ System _ Array _ System _ Object _ System _ Collections _ IComparer _](https://docs.microsoft.com/en-us/dotnet/api/system.array.binarysearch?view=netframework-4.7.2# System_Array_BinarySearch_System_Array_System_Object_System_Collections_IComparer_)