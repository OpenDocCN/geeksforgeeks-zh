# c# 中数组指定维度的元素总数

> 原文:[https://www . geeksforgeeks . org/c-sharp 数组中指定维度的元素总数/](https://www.geeksforgeeks.org/total-number-of-elements-in-a-specified-dimension-of-an-array-in-c-sharp/)

**阵列。GetLongLength(Int32)方法**用于获取一个 64 位整数，代表数组指定维度的元素个数。

**语法:**

```cs
public long GetLongLength (int dimension);
```

这里，*维*是要计算长度的数组的从零开始的维。

**返回值:**返回一个`64-bit`整数，代表指定维度的元素个数。

**异常:**如果*维度*小于零或大于等于*等级*，该方法抛出*指数。*

**示例:**

```cs
// C# program to illustrate the
// Array.GetLongLength() method
using System;

namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // Three-dimensional array.
        int[,, ] arr = new int[,, ] {
                                      { { 1, 2, 3 },
                                        { 4, 5, 6 },
                                        { 6, 7, 8 } 

                                      },

                                      { { 11, 12, 13 },
                                        { 14, 15, 16 },
                                        { 17, 18, 19 } 
                                      },

                                      { { 21, 22, 23 },
                                        { 24, 25, 26 },
                                        { 27, 28, 29 } 
                                      },
                                    };

        Console.Write("Total Number of Elements in"
                    + " first dimension of arr: ");

        // using GetLongLength Method
        Console.Write(arr.GetLongLength(0));

        // getting the type of returned value
        Console.WriteLine("\nType of returned Length: "
                        + (arr.GetLongLength(0)).GetType());

        // showing difference between GetLength
        // and GetLongLength method by getting
        // the type of the both method's
        // returned value

        Console.Write("\nTotal Number of Elements in "
                    + "second dimension of arr: ");

        // using GetLength Method
        Console.Write(arr.GetLength(1));

        // getting the type of returned value
        Console.WriteLine("\nType of returned Length: "
                        + (arr.GetLength(1)).GetType());

        Console.Write("\nTotal Number of Elements in "
                    + "second dimension of arr: ");

        // using GetLongLength() Method
        Console.Write(arr.GetLongLength(1));

        // getting the type of returned value
        Console.WriteLine("\nType of returned Length: "
                        + (arr.GetLongLength(1)).GetType());
    }
}
}
```

**Output:**

```cs
Total Number of Elements in first dimension of arr: 3
Type of returned Length: System.Int64

Total Number of Elements in second dimension of arr: 3
Type of returned Length: System.Int32

Total Number of Elements in second dimension of arr: 3
Type of returned Length: System.Int64

```

**注:**在上面的程序中，*T5【GetLength】T6*方法返回类型为`System.Int32`但是 *GetLongLength* 方法返回类型为`System.Int64`。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . getlonglength？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.getlonglength?view=netframework-4.7.2)