# C# Array.ConstrainedCopy() 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-array-constrainedcopy-method/](https://www.geeksforgeeks.org/c-sharp-array-constrainedcopy-method/)

此方法用于从指定的源索引开始复制数组中的一系列元素，并将它们粘贴到从指定的目标索引开始的另一个数组中。保证如果复制没有完全成功，所有更改都将被撤消。

## 语法

```cs
public static void ConstrainedCopy (Array sourceArray, int sourceIndex, 
Array destinationArray, int destinationIndex, int length);
```

## 参数

> `sourceArray`：是包含要复制的数据的数组。
> `sourceIndex`：它是代表源数组中开始复制的索引的 32 位整数。
> `destinationArray`：接收数据的是数组。
> `destinationIndex`：是代表目标数组中开始存储的索引的 32 位整数。
> `length`：表示要复制的元素数量的 32 位整数。

## 异常

*   `ArgumentNullException`：如果 `sourceArray` 或 `destinationArray` 为空。
*   `RankException`：如果 `sourceArray` 和 `destinationArray` 的等级不同。
*   `ArrayTypeMismatchException`：如果 `sourceArray` 类型与 `destinationArray` 类型既不相同也不从 `destinationArray` 类型派生。
*   `InvalidCastException`：`sourceArray` 中至少有一个元素不能转换为 `destinationArray` 的类型。
*   `ArgumentOutOfRangeException`：如果 `sourceIndex` 小于 `sourceArray` 第一维度的下界**或** `destinationIndex` 小于 `destinationArray` 第一维度的下界**或** `length` 小于零。
*   `ArgumentException`：如果 `length` 大于从 `sourceIndex` 到 `sourceArray` 末尾的元素数**或** `length` 大于从 `destinationIndex` 到 `destinationArray` 末尾的元素数。

下面的程序说明了 `Array.ConstrainedCopy(Array, Int32, Array, Int32, Int32)` 方法的使用：

### 示例 1

```cs
// C# program to demonstrate
// ConstrainedCopy() method
using System;
using System.Collections.Generic;

public class GFG {

// Main Method
    public static void Main()
    {

        try {

            // Creating and initializing new the String
            String[] srcArr = { "Sun", "Mon", "Tue", "Thu" };

            // Creating the object of empty String Array
            String[] destArr = new String[10];

            // Display the values of the myArr.
            Console.WriteLine("Initial Array:");

            // calling the PrintIndexAndValues()
            // method to print
            PrintIndexAndValues(srcArr);

            // getting a ConstrainedCopy in destArr
            // from srcArr using method ConstrainedCopy()
            Array.ConstrainedCopy(srcArr, 1, destArr, 0, 3);

            // Display the value of the destArr
            Console.WriteLine("Destination Array: ");

            // calling the PrintIndexAndValues()
            // method to print
            PrintIndexAndValues(destArr);
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (RankException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArrayTypeMismatchException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (InvalidCastException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArgumentOutOfRangeException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArgumentException e) {

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
}
```

### Output

```cs
Initial Array:
Sun
Mon
Tue
Thu

Destination Array: 
Mon
Tue
Thu
```

### 示例 2：适用于 `ArgumentNullException`

```cs
// C# program to demonstrate
// ConstrainedCopy() method
// For ArgumentNullException
using System;
using System.Collections.Generic;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Creating and initializing the
        // String Array with null
        String[] srcArr = null;

        // Creating the object of empty String Array
        String[] destArr = new String[10];

        // getting a ConstrainedCopy in destArr
        // from srcArr using method ConstrainedCopy()
        Console.WriteLine("Trying to get the ConstrainedCopy "
                         +"while srcArr is null");
        Console.WriteLine();
        Array.ConstrainedCopy(srcArr, 1, destArr, 0, 3);
```

// Display the value of the destArr.
`Console.WriteLine("Destination Array: ");`

// calling the `PrintIndexAndValues()`
// method to print
`PrintIndexAndValues(destArr);`
}
catch (`ArgumentNullException` e) {

`Console.Write("Exception Thrown: ");`
`Console.Write("{0}", e.GetType(), e.Message);`
}
catch (`RankException` e) {

`Console.Write("Exception Thrown: ");`
`Console.Write("{0}", e.GetType(), e.Message);`
}
catch (`ArrayTypeMismatchException` e) {

`Console.Write("Exception Thrown: ");`
`Console.Write("{0}", e.GetType(), e.Message);`
}
catch (`InvalidCastException` e) {

`Console.Write("Exception Thrown: ");`
`Console.Write("{0}", e.GetType(), e.Message);`
}
catch (`ArgumentOutOfRangeException` e) {

`Console.Write("Exception Thrown: ");`
`Console.Write("{0}", e.GetType(), e.Message);`
}
catch (`ArgumentException` e) {

`Console.Write("Exception Thrown: ");`
`Console.Write("{0}", e.GetType(), e.Message);`
}
}

// Defining the method
// `PrintIndexAndValues`
public static void `PrintIndexAndValues`(`String[] myArr`)
{
for (int i = 0; i < `myArr.Length`; i++) {

`Console.WriteLine("{0}", myArr[i]);`
}
`Console.WriteLine();`
}
}
```

Output:

```cs
Trying to get the ConstrainedCopy while srcArr is null

Exception Thrown: System.ArgumentNullException

```

例 3: 为`RankException`

```cs
// C# program to demonstrate
// ConstrainedCopy() method
// For RankException
using System;
using System.Collections.Generic;

public class GFG {

// Main Method
public static void Main()
{

try {

// Creating and initializing new the String
String[] srcArr = { "Sun", "Mon", "Tue", "Thu" };

// Creating the object of empty String Array
String[, ] destArr = new String[10, 5];

// Display the values of the myArr.
Console.WriteLine("Initial Array:");

// calling the PrintIndexAndValues()
// method to print
PrintIndexAndValues(srcArr);

// getting a ConstrainedCopy in destArr
// from srcArr using method ConstrainedCopy()
Console.WriteLine("Trying to get the ConstrainedCopy "
+"in destArr of rank 2");
Console.WriteLine("while rank of srcArr is 1");
Array.ConstrainedCopy(srcArr, 1, destArr, 0, 3);
}
catch (ArgumentNullException e) {

Console.Write("Exception Thrown: ");
Console.Write("{0}", e.GetType(), e.Message);
}
catch (RankException e) {

Console.Write("Exception Thrown: ");
Console.Write("{0}", e.GetType(), e.Message);
}
catch (ArrayTypeMismatchException e) {

Console.Write("Exception Thrown: ");
Console.Write("{0}", e.GetType(), e.Message);
}
catch (InvalidCastException e) {

Console.Write("Exception Thrown: ");
Console.Write("{0}", e.GetType(), e.Message);
}
catch (ArgumentOutOfRangeException e) {

Console.Write("Exception Thrown: ");
Console.Write("{0}", e.GetType(), e.Message);
}
catch (ArgumentException e) {

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
}
```

Output:

```cs
Initial Array:
Sun
Mon
Tue
Thu

Trying to get the ConstrainedCopy in destArr of rank 2
while rank of srcArr is 1
Exception Thrown: System.RankException

```

例 4: 为`ArrayTypeMismatchException`

```cs
// C# program to demonstrate
// ConstrainedCopy() method
// For ArrayTypeMismatchException
using System;
using System.Collections.Generic;

class GFG {

// Main Method
public static void Main()
{

try {

// Creating and initializing new the String
String[] srcArr = { "Sun", "Mon", "Tue", "Thu" };

// Creating the object of
// empty Integer Array
int[] destArr = new int[10];

// Display the values of the myArr.
Console.WriteLine("Initial Array:");
```

## 例 5: 为 argumentout of range exception

```cs
// C# program to demonstrate 
// ConstrainedCopy() method 
// For ArgumentOutOfRangeException
using System; 
using System.Collections.Generic;

public class GFG {

    // Main Method 
    public static void Main() 
    {
        try {
            // Creating and initializing 
            // new the String 
            String[] srcArr = {"Sun", "Mon", "Tue", "Thu"};

            // Creating the object of empty String Array 
            String[] destArr = new String[10];

            // Display the values of the myArr. 
            Console.WriteLine("Initial Array:");

            // calling the PrintIndexAndValues() 
            // method to print 
            PrintIndexAndValues(srcArr);

            // getting a ConstrainedCopy
            // in destArr from srcArr 
            // using method ConstrainedCopy() 
            Console.WriteLine("Trying to get the ConstrainedCopy"
                              +" of length less than zero");
            Array.ConstrainedCopy(srcArr, 1, destArr, 0, -1);
        }
        catch (ArgumentNullException e) {
            Console.Write("Exception Thrown: "); 
            Console.Write("{0}", e.GetType(), e.Message); 
        } 
        catch (RankException e) {
            Console.Write("Exception Thrown: "); 
            Console.Write("{0}", e.GetType(), e.Message); 
        } 
        catch (ArrayTypeMismatchException e) {
            Console.Write("Exception Thrown: "); 
            Console.Write("{0}", e.GetType(), e.Message); 
        } 
        catch (InvalidCastException e) {
            Console.Write("Exception Thrown: "); 
            Console.Write("{0}", e.GetType(), e.Message); 
        } 
        catch (ArgumentOutOfRangeException e) {
            Console.Write("Exception Thrown: "); 
            Console.Write("{0}", e.GetType(), e.Message); 
        } 
        catch (ArgumentException e) {
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
}
```

### Output

```cs
Initial Array:
Sun
Mon
Tue
Thu

Trying to get the ConstrainedCopy of length less than zero
Exception Thrown: System.ArgumentOutOfRangeException
```

## 示例 6: 适用于 参数异常

```cs
// C# program to demonstrate
// ConstrainedCopy() method
// For ArgumentException
using System;
using System.Collections.Generic;

public class GFG {

    // Main Method
    public static void Main()
    {
        try {
            // Creating and initializing new the String
            String[] srcArr = { "Sun", "Mon", "Tue", "Thu" };

            // Creating the object of empty String Array
            String[] destArr = new String[10];

            // Display the values of the myArr.
            Console.WriteLine("Initial Array:");

            // calling the PrintIndexAndValues()
            // method to print
            PrintIndexAndValues(srcArr);

            // getting a ConstrainedCopy 
            // in destArr from srcArr
            // using method ConstrainedCopy()
            Console.WriteLine("Trying to get the ConstrainedCopy"
                              +" of length is greater than the number ");
            Console.WriteLine("of elements from sourceIndex"
                              +" to the end of sourceArray.");
            Console.WriteLine();
            Array.ConstrainedCopy(srcArr, 1, destArr, 0, 4);
        }
        catch (ArgumentNullException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (RankException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArrayTypeMismatchException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (InvalidCastException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArgumentOutOfRangeException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArgumentException e) {
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
}
```

### Output

```cs
Initial Array:
Sun
Mon
Tue
Thu

Trying to get the ConstrainedCopy of length is greater than the number 
of elements from sourceIndex to the end of sourceArray.

Exception Thrown: System.ArgumentException
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.array.constrainedcopy?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.constrainedcopy?view=netframework-4.7.2)