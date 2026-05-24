# C# |数组。获取枚举器方法

> 原文:[https://www . geesforgeks . org/c-sharp-array-getenumerator-method/](https://www.geeksforgeeks.org/c-sharp-array-getenumerator-method/)

此方法用于返回数组的 IEnumerator。

**语法:**

```cs
public System.Collections.IEnumerator GetEnumerator ();
```

**返回值:**这个方法为数组返回一个 IEnumerator。

下面的程序说明了**数组的使用。获取枚举器**方法:

**例 1:**

```cs
// C# program to demonstrate
// GetEnumerator() method
using System;
using System.Collections;
using System.Collections.Generic;

public class GFG {

    // Main Method
    public static void Main()
    {

        // Creating and initializing new the String
        String[] myArr = {"Sun", "Mon", "Tue", "Thu"};

        // Display the values of the myArr.
        Console.Write("Initial Array: ");

        // calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(myArr);

        // getting the IEnumerator for the myArr
        IEnumerator myEnumerator = myArr.GetEnumerator();

        // calling the PrintIndexAndValues()
        // method to print
        Console.WriteLine("Enumerated value: ");
        PrintIndexAndValues(myEnumerator);
    }

    // Defining the method
    // PrintIndexAndValues
    public static void PrintIndexAndValues(String[] myArr)
    {
        for (int i = 0; i < myArr.Length; i++) {

            Console.Write("{0} ", myArr[i]);
        }
        Console.WriteLine();
        Console.WriteLine();
    }

    // Overriding the method
    // PrintIndexAndValues
    public static void PrintIndexAndValues(IEnumerator myEnumerator)
    {
        int i = 0;
        while ((myEnumerator.MoveNext()) && 
          (myEnumerator.Current != null)) {

            Console.WriteLine("[{0}] {1}", i++,
                         myEnumerator.Current);
        }
    }
}
```

**Output:**

```cs
Initial Array: Sun Mon Tue Thu 

Enumerated value: 
[0] Sun
[1] Mon
[2] Tue
[3] Thu

```

**例 2:**

```cs
// C# program to demonstrate
// GetEnumerator() method
// For int value
using System;
using System.Collections;
using System.Collections.Generic;

public class GFG {

    // Main Method
    public static void Main()
    {

        // Creating and initializing new the int
        int[] myArr = {10, 20, 30, 40};

        // Display the values of the myArr.
        Console.Write("Initial Array: ");

        // calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(myArr);

        // getting the IEnumerator for the myArr
        IEnumerator myEnumerator = myArr.GetEnumerator();

        // calling the PrintIndexAndValues()
        // method to print
        Console.WriteLine("Enumerated value: ");
        PrintIndexAndValues(myEnumerator);
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

    // Overriding the method
    // PrintIndexAndValues
    public static void PrintIndexAndValues(IEnumerator myEnumerator)
    {
        int i = 1;
        while ((myEnumerator.MoveNext()) && 
          (myEnumerator.Current != null)) {

            Console.WriteLine("{0}> {1} ", i++, 
                          myEnumerator.Current);
        }
    }
}
```

**Output:**

```cs
Initial Array: 10 20 30 40 

Enumerated value: 
1> 10 
2> 20 
3> 30 
4> 40

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . getenumerator？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.getenumerator?view=netframework-4.7.2)