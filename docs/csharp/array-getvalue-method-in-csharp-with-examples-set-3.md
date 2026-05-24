# 阵列。C# 中的 GetValue()方法，带示例| Set–3

> 原文:[https://www . geesforgeks . org/array-getvalue-method-in-csharp-with-examples-set-3/](https://www.geeksforgeeks.org/array-getvalue-method-in-csharp-with-examples-set-3/)

数组。C# 中的 GetValue()方法用于获取当前[数组](https://www.geeksforgeeks.org/c-sharp-arrays/)中指定元素的值。该方法的重载列表中共有 8 种方法，如下所示:

*   [**阵。GetValue(Int32，Int32)**](https://www.geeksforgeeks.org/array-getvalue-method-in-csharp-with-examples-set-1/)
*   [**阵。GetValue(Int64，Int64)**](https://www.geeksforgeeks.org/array-getvalue-method-in-csharp-with-examples-set-1/)
*   [**阵。GetValue(Int32)**](https://www.geeksforgeeks.org/array-getvalue-method-in-csharp-with-examples-set-2/)
*   [**阵。GetValue(Int64)**](https://www.geeksforgeeks.org/array-getvalue-method-in-csharp-with-examples-set-2/)
*   **阵列。GetValue(Int32，Int32，Int32)**
*   **阵列。GetValue(Int64，Int64，Int64)**
*   **Array.GetValue（Int32[]）**
*   **Array.GetValue（Int64[]）**

在本文中，我们将解释**数组。GetValue(Int32，Int32，Int32)** 和**数组。GetValue(Int64，Int64，Int64)** 方法。

**阵列。GetValue(Int32，Int32，Int32)** 方法用于获取三维数组中指定位置的值。索引被指定为 32 位整数。

**语法:**

```cs
public object GetValue (int index1, int index2, int index3);

```

在这里，

*   **“index 1”**是元素所在数组的个数。
*   **“index 2”**是元素所在行的索引。
*   **“index 3”**是元素所在列的索引。

**返回:**该方法返回由 3D 数组中传递的参数定义的指定索引处的元素。该值是一个 32 位整数值。

**异常:**

*   **参数异常:**当前数组没有精确的三维。
*   **IndexOutOfRangeException:**如果 index1 或 index2 或 index3 在当前数组对应维度的有效索引范围之外。

**阵列。GetValue(Int64，Int64，Int64)** 方法用于获取三维数组中指定位置的值。索引被指定为 64 位整数。

**语法:**

```cs
public object GetValue (long index1, long index2, long index3);

```

在这里，

*   **“index 1”**是元素所在数组的个数。
*   **“index 2”**是元素所在行的索引。
*   **“index 3”**是元素所在列的索引。

**返回:**该方法返回由 3D 数组中传递的参数定义的指定索引处的元素。该值是一个 64 位整数值。

**异常:**

*   **ArgumentException:** 当前数组没有正好三维。
*   **IndexOutOfRangeException:**如果 index1 或 index2 或 index2 超出当前数组相应维度的有效索引范围。

**例 1:**

## C#

```cs
// C# program to demonstrate
// Array.GetValue(Int32, Int32, Int32)
// and array.GetValue(Int64, Int64, Int64)
// method
using System;
public class GFG {

public static void Main() {

    // declare a character
    // array of size 2x2x3
    // 2 row and 3 column
    // numbe of array is 2
    char[, , ] arr = new char[2, 2, 3]{

        {// array 1
         {'A', 'B', 'C'},
         {'D', 'E', 'F'}

        },
        {// array 2
         {'G', 'H', 'I'},
         {'J', 'K', 'L'}}

    };

    // using GetValue(Int32, Int32, Int32) and
    // GetValue(Int64, Int64, Int64) method
    for (int i = 0; i < 2; i++) {
      for (int j = 0; j < 2; j++) {
        for (int k = 0; k < 3; k++) {
          Console.WriteLine("element at index [{0}, {1}, {2}] is : {3}", i, j,
                            k, arr.GetValue(i, j, k));
        }
      }
    }
  }
}
```

**Output**

```cs
element at index [0, 0, 0] is : A
element at index [0, 0, 1] is : B
element at index [0, 0, 2] is : C
element at index [0, 1, 0] is : D
element at index [0, 1, 1] is : E
element at index [0, 1, 2] is : F
element at index [1, 0, 0] is : G
element at index [1, 0, 1] is : H
element at index [1, 0, 2] is : I
element at index [1, 1, 0] is : J
element at index [1, 1, 1] is : K
element at index [1, 1, 2] is : L

```

**例 2:**

## C#

```cs
// C# program to demonstrate
// Array.GetValue(Int32, Int32, Int32)
// and array.GetValue(Int64, Int64, Int64)
// method
using System;

public class GFG {

    public static void Main()
    {
        // declare a character
          // array of size 2x2x3
        // 2 row and 3 column
        // numbe of array is 2
        string[,, ] arr = new string[2, 2, 3];

        // use "SetValue()" method to set
        // the value at specified index
        arr.SetValue("C++", 0, 0, 0);
        arr.SetValue("Java", 0, 0, 1);
        arr.SetValue("C#", 0, 0, 2);
        arr.SetValue("Perl", 0, 1, 0);
        arr.SetValue("Python", 0, 1, 1);
        arr.SetValue("PHP", 0, 1, 2);
        arr.SetValue("GO", 1, 0, 0);
        arr.SetValue("Ruby", 1, 0, 1);
        arr.SetValue("F#", 1, 0, 2);
        arr.SetValue("JavaScript", 1, 1, 0);
        arr.SetValue("SQL", 1, 1, 1);
        arr.SetValue("kotlin", 1, 1, 2);

        // using GetValue(Int32, Int32, Int32) and
        // GetValue(Int64, Int64, Int64) method
        for (int i = 0; i < 2; i++) {
            for (int j = 0; j < 2; j++) {
                for (int k = 0; k < 3; k++) {
                    Console.WriteLine("element at index [{0}, {1}, {2}] is : {3}",
                                                  i, j, k, arr.GetValue(i, j, k));
                }
            }
        }
    }
}
```

**Output**

```cs
element at index [0, 0, 0] is : C++
element at index [0, 0, 1] is : Java
element at index [0, 0, 2] is : C#
element at index [0, 1, 0] is : Perl
element at index [0, 1, 1] is : Python
element at index [0, 1, 2] is : PHP
element at index [1, 0, 0] is : GO
element at index [1, 0, 1] is : Ruby
element at index [1, 0, 2] is : F#
element at index [1, 1, 0] is : JavaScript
element at index [1, 1, 1] is : SQL
element at index [1, 1, 2] is : kotlin

```

**注意:**对于在线编译器，不能使用 32 位或 64 位整数。对 32 或 64 位整数使用脱机编译器。