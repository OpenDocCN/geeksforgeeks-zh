# C# |将一种类型的数组转换为另一种类型的数组

> 原文:[https://www . geesforgeks . org/c-sharp-将一种类型的数组转换为另一种类型的数组/](https://www.geeksforgeeks.org/c-sharp-converting-an-array-of-one-type-to-an-array-of-another-type/)

**阵列。ConvertAll(TInput[]，Converter < TInput，TOutput >)方法**用于将一种类型的数组转换为另一种类型的数组。

**语法:**

```cs
public static TOutput[] ConvertAll<TInput,TOutput> (TInput[] array, 
Converter<TInput,TOutput> converter);
```

这里 **TInput** 和 **TOutput** 分别是源阵和目标阵。

**参数:**

> **数组:**是一维的，从零开始的数组，转换成目标类型。
> **转换器:**它是一个将每个元素从一种类型转换成另一种类型的转换器。

**返回值:**该方法返回一个目标类型的数组，该数组包含来自源数组的转换元素。

**异常:**如果*数组*为空或者*转换器*为空，该方法抛出 **ArgumentNullException** 。

下面的程序说明了**数组的使用。ConvertAll(TInput[]，Converter < TInput，TOutput >)方法**

**例 1:**

```cs
// C# program to demonstrate
// Array.ConvertAll() Method
using System;
using System.Collections.Generic;

public class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Creating and initializing
            // new the Array of int
            int[] myArr = {10, 20, 30, 40};

            // Display the values of the myArr.
            Console.WriteLine("Initial Array:");

            // calling the PrintIndexAndValues()
            // method to print
            PrintIndexAndValues(myArr);

            // converting int myArr to String conarr
            String[] conarr = Array.ConvertAll(myArr, 
              new Converter<int, String>(intToString));

            // Display the values of the myArr.
            Console.WriteLine("Converted Array:");

            // calling the PrintIndexAndValues()
            // method to print
            PrintIndexAndValues(conarr);
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining the method
    // PrintIndexAndValues
    public static void PrintIndexAndValues(String[] myArr)
    {
        for (int i = 0; i < myArr.Length; i++) {

            Console.WriteLine("{0}", myArr[i]);
        }
        Console.WriteLine();
    }

    // Defining the method
    // PrintIndexAndValues
    public static void PrintIndexAndValues(int[] myArr)
    {
        for (int i = 0; i < myArr.Length; i++) {

            Console.WriteLine("{0}", myArr[i]);
        }
        Console.WriteLine();
    }

    // Defining the method
    // intToString
    public static String intToString(int pf)
    {
        return pf.ToString();
    }
}
```

**Output:**

```cs
Initial Array:
10
20
30
40

Converted Array:
10
20
30
40

```

**例 2:**

```cs
// C# program to demonstrate
// Array.ConvertAll() Method
using System;
using System.Collections.Generic;

public class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Creating and initializing new 
            // the Array of int with null value
            int[] myArr = null;

            // converting int myArr to String conarr
            String[] conarr = Array.ConvertAll(myArr, 
             new Converter<int, String>(intToString));

            // calling the PrintIndexAndValues()
            // method to print
            PrintIndexAndValues(conarr);
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining the method
    // PrintIndexAndValues
    public static void PrintIndexAndValues(String[] myArr)
    {
        for (int i = 0; i < myArr.Length; i++) {

            Console.WriteLine("{0}", myArr[i]);
        }
        Console.WriteLine();
    }

    // Defining the method
    // intToString
    public static String intToString(int pf)
    {
        return pf.ToString();
    }
}
```

**Output:**

```cs
Exception Thrown: System.ArgumentNullException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . convertall？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.convertall?view=netframework-4.7.2)