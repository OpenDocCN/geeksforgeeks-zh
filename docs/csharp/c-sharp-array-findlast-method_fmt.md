# C# 数组.FindLast()方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-array-findlast-method/](https://www.geeksforgeeks.org/c-sharp-array-findlast-method/)

此方法用于搜索与指定谓词定义的条件相匹配的元素，返回整个数组中最后一次出现的。

## 语法

```cs
public static T FindLast<T> (T[] array, Predicate<T> match);
```

## 参数

- `array`：一维的，从零开始搜索的数组。
- `match`：定义要搜索的元素的条件的谓词。

## 返回值

如果找到匹配指定谓词定义的条件的最后一个元素，则该方法返回该元素，否则返回类型 `T` 的默认值。

## 异常

如果 `array` 为空或 `match` 为空，则此方法抛出 `ArgumentNullException`。

下面的程序说明了 `Array.FindLast(T[], Predicate<T>)` 方法的使用：

## 示例1

```cs
// C# program to demonstrate
// Array.FindLast(T[], Predicate<T>)
// Method
using System;
using System.Collections.Generic;

public class GFG {

    // Main Method
    public static void Main()
    {
        try {
            // Creating and initializing
            // new the String
            String[] myArr = {"Sun", "Son", "Tue", "Thu"};

            // Display the values of the myArr.
            Console.WriteLine("Initial Array:");

            // calling the PrintIndexAndValues()
            // method to print
            PrintIndexAndValues(myArr);

            // getting a last element with required
            // condition using method FindLast()
            string value = Array.FindLast(myArr,
                   element => element.StartsWith("S",
                      StringComparison.Ordinal));

            // Display the value of
            // the found element.
            Console.Write("Last occurrence: ");

            // printing the string
            // following the condition
            Console.Write("{0}", value);
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
}
```

**输出：**

```cs
Initial Array:
Sun
Son
Tue
Thu

Last occurrence: Son
```

## 示例2

```cs
// C# program to demonstrate
// Array.FindLast(T[], Predicate<T>)
// Method
using System;
using System.Collections.Generic;

public class GFG {

    // Main Method
    public static void Main()
    {
        try {
            // Creating and initializing
            // new Array String with null
            String[] myArr = null;

            // getting a last element with required
            // condition using method FindLast()
            string value = Array.FindLast(myArr,
                element => element.StartsWith("S",
                       StringComparison.Ordinal));

            // Display the value of
            // the found element.
            Console.Write("Last occurrence: ");

            // printing the string
            // following the condition
            Console.Write("{0}", value);
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
}
```

**输出：**

```cs
Exception Thrown: System.ArgumentNullException
```

## 参考

- [https://docs.microsoft.com/en-us/dotnet/api/system.array.findlast?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.array.findlast?view=netframework-4.7.2)