# 阵列。C# 中的 GetValue()方法，带示例| Set–1

> 原文:[https://www . geesforgeks . org/array-getvalue-method-in-csharp-with-examples-set-1/](https://www.geeksforgeeks.org/array-getvalue-method-in-csharp-with-examples-set-1/)

数组。C# 中的 GetValue()方法用于获取当前[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)中指定元素的值。本法过载列表共 8 法，如下:

***   阵。GetValue（Int32，Int32）*   数组。GetValue（Int64，Int64）*   数组。GetValue（Int32）*   数组。GetValue（Int64）*   数组。GetValue（Int32，Int32，Int32）*   数组。GetValue（Int64，Int64，Int64）*   GetValue（Int32[]）*   GetValue（Int64[]）**

下面，我们来讲解前两种方法即 Array。GetValue(Int32，Int32)和 Array。GetValue(Int64，Int64)方法。

**GetValue(Int32，Int32)方法**用于获取二维数组中指定位置的值。索引被指定为 32 位整数。

**语法:**

```cs
public object GetValue (int index1, int index2);
```

在这里，

*   **“index 1”**是元素所在行的索引。
*   **“index 2”**是元素所在列的索引。

**Return:** 该方法返回由 2D 数组中传递的参数定义的指定索引处的元素。

**异常:**

*   **ArgumentException:** 当前数组没有正好两个维度。
*   **IndexOutOfRangeException:**index 1 或 index2 超出了当前数组相应维度的有效索引范围。

**GetValue(Int64，Int64)方法**用于获取二维数组中指定位置的值。索引被指定为 64 位整数。

**语法:**

```cs
public object GetValue (long index1, long index2);
```

在这里，

*   **“index 1”**是元素所在行的索引。
*   **“index 2”**是元素所在列的索引。

**Return:** 该方法返回由 2D 数组中传递的参数定义的指定索引处的元素。

**异常:**

*   **ArgumentException:** 当前数组没有正好两个维度。
*   **IndexOutOfRangeException:**index 1 或 index2 超出了当前数组相应维度的有效索引范围。

**例 1:**

```cs
// C# program to demonstrate Array.GetValue(Int32, Int32) 
// and array.GetValue(Int64 , Int64) method 
using System;
public class GFG {

public static void Main()
{
    // declare a character array 
    char[,] arr = new char[3,2]
    { 
        { 'A', 'B' },
        { 'C', 'D' },
        { 'E', 'F' } 

    };

    // using  GetValue(Int32, Int32) and 
    // GetValue(Int64, Int64) method
    Console.WriteLine("element at index [0,0] is : " + arr.GetValue(0,0));
    Console.WriteLine("element at index [1,1] is : " + arr.GetValue(1,1));
    Console.WriteLine("element at index [0,1] is : " + arr.GetValue(0,1));
    Console.WriteLine("element at index [1,0] is : " + arr.GetValue(1,0));
    Console.WriteLine("element at index [2,0] is : " + arr.GetValue(2,0));
    Console.WriteLine("element at index [2,1] is : " + arr.GetValue(2,1));
}
}
```

输出:

```cs
element at index [0,0] is : A
element at index [1,1] is : D
element at index [0,1] is : B
element at index [1,0] is : C
element at index [2,0] is : E
element at index [2,1] is : F

```

**例 2:**

```cs
// C# program to demonstrate Array.GetValue(Int32, Int32) 
// and array.GetValue(Int64 , Int64) method 
using System;
public class GFG {

public static void Main()
{
    // declare a string array 
    string[,] arr = new string[3,2];

      // use "SetValue()" method to set 
      // the value at specified index
      arr.SetValue( "C++", 0, 0 );
      arr.SetValue( "Java", 0, 1 );
      arr.SetValue( "C#", 1, 0 );
      arr.SetValue( "Perl", 1, 1 );
      arr.SetValue( "Python", 2, 0 );
      arr.SetValue( "PHP", 2, 1 );

    /*the array look like
      | C++ |    | Java| 
      | C#  |    | Perl|
      | python|  | PHP |
    */

    // Using GetValue(Int32, Int32) and
    // GetValue(Int64, Int64) method
    Console.WriteLine("element at index [0,0] is : " + arr.GetValue(0,0));
    Console.WriteLine("element at index [1,1] is : " + arr.GetValue(1,1));
    Console.WriteLine("element at index [0,1] is : " + arr.GetValue(0,1));
    Console.WriteLine("element at index [1,0] is : " + arr.GetValue(1,0));
    Console.WriteLine("element at index [2,0] is : " + arr.GetValue(2,0));
    Console.WriteLine("element at index [2,1] is : " + arr.GetValue(2,1));
}
}
```

**输出:**

```cs
element at index [0, 0] is : C++
element at index [1, 1] is : Perl
element at index [0, 1] is : Java
element at index [1, 0] is : C#
element at index [2, 0] is : Python
element at index [2, 1] is : PHP

```

**注意:**对于在线编译器，不能使用 32 位或 64 位整数。对 32 或 64 位整数使用脱机编译器。