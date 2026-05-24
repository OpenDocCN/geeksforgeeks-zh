# 如何在 C# 中求数组的秩

> 原文:[https://www . geeksforgeeks . org/如何找到 c-sharp 中的数组秩/](https://www.geeksforgeeks.org/how-to-find-the-rank-of-an-array-in-c-sharp/)

**阵列。等级属性**用于获取[阵](https://www.geeksforgeeks.org/c-sharp-arrays/)的等级。秩是数组的维数。例如，一维数组返回 1，二维数组返回 2，依此类推。

**语法:**

```cs
public int Rank { get; }
```

**属性值:**返回*系统类型数组的秩(维数)。Int32* 。

以下程序说明了上述属性的使用:

**例 1:**

```cs
// C# program to illustrate the
// Array.Rank Property
using System;
namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // declares a 1D Array of string.
        string[] weekDays;

        // allocating memory for days.
        weekDays = new string[] {"Sun", "Mon", "Tue", "Wed",
                                      "Thu", "Fri", "Sat" };

        // using Rank Property
        Console.WriteLine("Dimension of weekDays array: " 
                                       + weekDays.Rank);
    }
}
}
```

**Output:**

```cs
Dimension of weekDays array: 1

```

**例 2:**

```cs
// C# program to illustrate the
// Array.Rank Property
using System;
namespace geeksforgeeks {

class GFG {

    // Main Method
    public static void Main()
    {

        // declaring an 2-D array
        int[, ] arr2d = new int[4, 2];

        // declaring an 3-D array
        int[,, ] arr3d = new int[4, 2, 3];

        // declaring an jagged array
        int[][] jdarr = new int[2][];

        // using Rank Property
        Console.WriteLine("Dimension of arr2d array: " 
                                        + arr2d.Rank);

        Console.WriteLine("Dimension of arr3d array: " 
                                        + arr3d.Rank);

        // for the jagged array it 
        // will always return 1
        Console.WriteLine("Dimension of jdarr array: " 
                                        + jdarr.Rank);
    }
}
}
```

**Output:**

```cs
Dimension of arr2d array: 2
Dimension of arr3d array: 3
Dimension of jdarr array: 1

```

**注:**

*   一个[交错数组(数组的数组)](https://www.geeksforgeeks.org/c-jagged-arrays/)是一维数组，所以它的 Rank 属性的值是 1。
*   检索该属性的值是一个 O(1)操作。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . rank？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.rank?view=netframework-4.7.2)