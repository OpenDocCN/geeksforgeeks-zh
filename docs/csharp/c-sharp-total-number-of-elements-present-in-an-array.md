# C# |数组中存在的元素总数

> 原文:[https://www . geeksforgeeks . org/c-sharp-数组中存在的元素总数/](https://www.geeksforgeeks.org/c-sharp-total-number-of-elements-present-in-an-array/)

**阵列。GetLength(Int32)方法**用于查找数组指定维度中存在的元素总数。
**语法:**

```cs
public int GetLength (int dimension);
```

这里*维*是需要确定长度的数组的从零开始的维。
**返回值:**该方法的返回类型为**系统。Int32** 。此方法返回一个 32 位整数，表示指定维度中的元素数量。
**异常:**如果*维度*的值小于零或者*维度*的值等于或大于[等级](https://docs.microsoft.com/en-us/dotnet/api/system.array.rank?view=netcore-2.1# System_Array_Rank)，该方法将给出*indexout of range Exception*。
下面给出一些例子，以便更好地理解实现:
**例子 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// use of GetLength() method
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // create and initialize array
        int[] myarray = {445, 44, 66, 6666667, 78, 878, 1};

        // Display the array
        Console.WriteLine("The elements of myarray :");

        foreach(int i in myarray)
        {
            Console.WriteLine(i);
        }

        // Find the number of element in myarray
        int result = myarray.GetLength(0);
        Console.WriteLine("Total Elements: {0}", result);
    }
}
```

**Output:** 

```cs
The elements of myarray :
445
44
66
6666667
78
878
1
Total Elements: 7
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to check arrays contain
// same number of elements or not
using System;

public class GFG {

    // Main method
    static public void Main()
    {

        // create and initializing array
        int[] myarray1 = {100, 0, 400, 660, 700, 809, 0};
        int[] myarray2 = {100, 0, 400, 660, 700};
        int[] myarray3 = {100, 0, 400, 660, 700, 809, 0};

        // Find the number of element in myarray
        // using GetLength() method
        int result1 = myarray1.GetLength(0);
        int result2 = myarray2.GetLength(0);
        int result3 = myarray3.GetLength(0);

        // Check if myarray1, myarray2, myarray3
        // contain the same number of elements or not
        Console.WriteLine("myarray1 and myarray2: {0}",
                             Equals(result1, result2));

        Console.WriteLine("myarray1 and myarray3: {0}",
                             Equals(result1, result3));
    }
}
```

**Output:** 

```cs
myarray1 and myarray2: False
myarray1 and myarray3: True
```

**参考:**[https://docs . Microsoft . com/en-us/dotnet/API/system . array . getlength？view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.array.getlength?view=netcore-2.1)