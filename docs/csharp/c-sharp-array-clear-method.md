# C# |数组。清除()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-array-clear-method/](https://www.geeksforgeeks.org/c-sharp-array-clear-method/)

此方法用于将数组中的元素范围设置为每个元素类型的默认值。

**语法:**

```cs
public static void Clear (Array array, int index, int length);
```

**参数:**

> **数组:**是需要清除元素的数组。
> **指数:**它是元素清除范围的起始指数。
> **长度:**是需要清除的元素数量。

**异常:**

*   **ArgumentNullException:** 如果数组为空
*   **indexout of range exception:**如果*索引*小于*数组* **或**的下限，则*长度*小于零**或***索引*和*长度*之和大于*数组*的大小。

下面是举例说明**数组。Clear()** 方法:

**例 1:**

```cs
// C# program to demonstrate Array.Clear()
// method for int type value
using System;
using System.Collections.Generic;

public class GFG {

    // Main Method
    public static void Main()
    {

        // Creating and initializing new the String
        int[] myArr = {10, 20, 30, 40};

        // Display the values of the myArr.
        Console.WriteLine("Array Before Operation:");

        // calling the PrintIndexAndValues() method 
        PrintIndexAndValues(myArr);
        Console.WriteLine();

        Array.Clear(myArr, 1, 2);

        // Display the values of myArr
        Console.WriteLine("Array After Operation:");

        // calling the PrintIndexAndValues() method
        PrintIndexAndValues(myArr);
    }

    // Defining the method PrintIndexAndValues 
    public static void PrintIndexAndValues(int[] myArr)
    {
        for (int i = 0; i < myArr.Length; i++) {
            Console.WriteLine("{0}", myArr[i]);
        }
    }
}
```

**Output:**

```cs
Array Before Operation:
10
20
30
40

Array After Operation:
10
0
0
40

```

**示例 2:** 适用于*参数异常*

```cs
// C# program to demonstrate
// Array.Clear() method
// for ArgumentNullException
using System;
using System.Collections.Generic;

public class GFG {

    public static void Main()
    {

        try {

            // Creating and initializing 
            // new the Int with null
            int[] myArr = null;

            // Clearing the myArr
            // using Clear() method
            Console.WriteLine("Try to clear the element from null Array:");
            Array.Clear(myArr, 1, 2);

            // Display the values of myArr
            Console.WriteLine("Array after operation :");

            // calling the PrintIndexAndValues() method 
            PrintIndexAndValues(myArr);
        }
        catch (ArgumentNullException e) {

            Console.WriteLine();
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (IndexOutOfRangeException e) {

            Console.WriteLine();
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining the method PrintIndexAndValues 
    public static void PrintIndexAndValues(int[] myArr)
    {
        for (int i = 0; i < myArr.Length; i++) {
            Console.WriteLine("{0}", myArr[i]);
        }
    }
}
```

**Output:**

```cs
Try to clear the element from null Array:

Exception Thrown: System.ArgumentNullException

```

**示例 3:** 适用于 *IndexOutOfRangeException*

```cs
// C# program to demonstrate
// Array.Clear() method
// for IndexOutOfRangeException
using System;
using System.Collections.Generic;

public class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Creating and initializing new Int array
            int[] myArr = {10, 20, 30, 40};

            // Display the values of myArr
            Console.WriteLine("Array Before Operation:");

            // calling the PrintIndexAndValues() method
            PrintIndexAndValues(myArr);
            Console.WriteLine();

            // Clearing the myArr
            // using Clear() method
            Console.WriteLine("Taking index out of bound:");
            Array.Clear(myArr, -1, 2);

            // Display the values of myArr
            Console.WriteLine("Array After Operation:");

            // calling the PrintIndexAndValues() method 
            PrintIndexAndValues(myArr);
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown :");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (IndexOutOfRangeException e) {
            Console.Write("Exception Thrown :");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining the method PrintIndexAndValues 
    public static void PrintIndexAndValues(int[] myArr)
    {
        for (int i = 0; i < myArr.Length; i++) {
            Console.WriteLine("{0}", myArr[i]);
        }
    }
}
```

**Output:**

```cs
Array Before Operation:
10
20
30
40

Taking index out of bound:
Exception Thrown :System.IndexOutOfRangeException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . array . clear？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.clear?view=netframework-4.7.2)