# 阵列。BinarySearch(数组、对象)方法，用 C# 举例

> 原文:[https://www . geeksforgeeks . org/array-binarysearcharray-object-method-with-examples-in-c-sharp/](https://www.geeksforgeeks.org/array-binarysearcharray-object-method-with-examples-in-c-sharp/)

此方法用于通过使用由数组的每个元素和指定的对象实现的 IComparable 接口，在整个一维排序的[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)中搜索特定的元素。

**语法:**

```cs
public static int BinarySearch (Array array, object value);
```

**参数:**

> **数组:**是要搜索的排序后的一维数组。
> 
> **值:**是要搜索的对象。

**返回值:**如果找到*值*，则返回指定的*数组*中指定的*值*的索引，否则返回负数。返回值有如下几种不同的情况:

*   如果在*数组*中没有找到*值*并且*值*小于一个或多个元素，则返回的负数是大于*值*的第一个元素的索引的按位补码。
*   如果找不到*值*并且*值*大于数组中的所有元素，则返回的负数是(最后一个元素的索引加 1)的按位补数。
*   如果使用非排序数组调用此方法，返回值可能不正确，并且可能返回负数，即使数组中存在*值*。

**异常:**

*   **参数空异常:**如果*阵*为*空*。
*   **rankeexception:**如果*阵*是多维的。
*   **参数异常:**如果*值*的类型与*数组*的元素不兼容。
*   **无效操作异常:**如果*值*没有实现 IComparable 接口，并且搜索遇到没有实现 IComparable 接口的元素。

以下程序说明了上述方法:

**例 1:**

```cs
// C# program to illustrate the 
// Array.BinarySearch(Array, Object)
// Method
using System;

class GFG {

    // Main Method
    public static void Main(String[] args) {

    // taking an 1-D Array
    int[] arr = new int[7] {1,5,7,4,6,2,3};

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

// containg BinarySearch Method
static void result(int[] arr2, object k) {

    // using the method
    int res = Array.BinarySearch(arr2, k);

    if (res < 0)
    {
        Console.WriteLine("\nThe element to search for "+
                            "({0}) is not found.", k);
    }

    else
    {
        Console.WriteLine("The element to search for "+
                    "({0}) is at index {1}.", k, res);
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

```cs
// C# program to illustrate the 
// Array.BinarySearch(Array, Object)
// Method
using System;

class GFG {

    // Main Method
    public static void Main(String[] args) {

    // taking an 1-D Array
    int[] arr = new int[7] {1,5,7,4,6,2,3};

    // for this method array
    // must be sorted
    Array.Sort(arr);

    Console.Write("The elements of Sorted Array: ");

    // calling the method to
    // print the values
    display(arr);

    // it will return a negative value as 
    // 9 is not present in the array
    Console.WriteLine("\nIndex of 9 is: "+ 
               Array.BinarySearch(arr,8));

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

**要点:**

*   对于这种方法，数组必须按排序顺序，即升序排列。
*   此方法不支持搜索包含负索引的数组。
*   允许重复元素。如果数组包含多个等于该值的元素，则该方法只返回其中一个实例的索引，而不一定是第一个实例的索引。
*   *null* 总是可以与任何其他引用类型进行比较；因此，与 null 进行比较不会产生异常。
*   这个方法是`O(log n)`运算，其中 n 是数组的长度。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . binary search？view = net framework-4 . 7 . 2 # System _ Array _ binary search _ System _ Array _ System _ Object _](https://docs.microsoft.com/en-us/dotnet/api/system.array.binarysearch?view=netframework-4.7.2# System_Array_BinarySearch_System_Array_System_Object_)