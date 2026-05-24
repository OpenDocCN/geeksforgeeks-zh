# C# |对数组的每个元素执行指定的动作

> 原文:[https://www . geesforgeks . org/c-sharp-对数组的每个元素执行指定的操作/](https://www.geeksforgeeks.org/c-sharp-performing-specified-action-on-each-element-of-array/)

**阵列。ForEach(T[]，Action < T >)方法**用于对指定数组的每个元素执行指定的操作。

**语法:**

```cs
public static void ForEach<T> (T[] array, Action<T> action);
```

**参数:**

> **数组:**要对其元素执行操作的一维、从零开始的数组。
> **动作:**对*阵*各元素执行的动作。

**异常:**此方法抛出 **ArgumentNullException** 数组为空或动作为空。
下面的程序说明了**阵列的使用。ForEach(T[]，Action)** 方法:
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Array.ForEach(T[], Action<T>)
// Method
using System;
using System.Collections.Generic;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Creating and initializing
            // new Array of int
            int[] myArr = { 2, 3, 4, 5 };

            // Display the values of the myArr.
            Console.Write("Initial Array: ");

            // calling the PrintIndexAndValues()
            // method to print
            PrintIndexAndValues(myArr);

            // set a delegate for
            // the SetSquares method
            Action<int> action = new Action<int>(SetSquares);

            // performing the action
            // using ForEach() method
            Array.ForEach(myArr, action);
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining the method
    // PrintIndexAndValues
    public static void PrintIndexAndValues(int[] myArr)
    {
        for (int i = 0; i < myArr.Length; i++) {

            Console.Write("{0} ", myArr[i]);
        }
        Console.WriteLine();
        Console.WriteLine();
    }

    // Defining the method
    // ShowSquares
    private static void SetSquares(int val)
    {
        Console.WriteLine("{0} squared = {1}",
                              val, val * val);
    }
}
```

**Output:** 

```cs
Initial Array: 2 3 4 5 

2 squared = 4
3 squared = 9
4 squared = 16
5 squared = 25
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Array.ForEach(T[], Action<T>)
// Method
using System;
using System.Collections.Generic;

public class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Creating and initializing
            // new Array of with null
            int[] myArr = null;

            // set a delegate for
            // the Set Squares method
            Action<int> action = new Action<int>(SetSquares);

            // performing the action
            // using ForEach() method
            Console.WriteLine("Trying to perform "
                       +"action on a null Array");
            Console.WriteLine();
            Array.ForEach(myArr, action);
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining the method
    // PrintIndexAndValues
    public static void PrintIndexAndValues(int[] myArr)
    {
        for (int i = 0; i < myArr.Length; i++) {

            Console.Write("{0} ", myArr[i]);
        }
        Console.WriteLine();
        Console.WriteLine();
    }

    // Defining the method
    // ShowSquares
    private static void SetSquares(int val)
    {
        Console.WriteLine("{0} squared = {1}", val, val * val);
    }
}
```

**Output:** 

```cs
Trying to perform action on a null Array

Exception Thrown: System.ArgumentNullException
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . foreach？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.foreach?view=netframework-4.7.2)