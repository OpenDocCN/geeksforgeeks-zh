# 日期时间。C# 中的 FromOADate()方法

> 原文:[https://www . geesforgeks . org/datetime-from oadate-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-fromoadate-method-in-c-sharp/)

**日期时间。from loadate(Double)方法**用于返回一个相当于指定的 OLE 自动化日期的日期时间。

> **语法:**public static DateTime from oad ate(double d)；
> 这里，它采用一个 OLE 自动化日期值。
> 
> **返回值:**这个方法返回一个表示和 d 相同日期和时间的对象
> 
> **异常:**如果日期不是有效的 OLE 自动化日期值，该方法将给出**参数异常**。

以下程序说明了*日期时间的使用。从加载状态(双)*方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTime.FromOADate(Int64) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // converting 657435.0 OLE 
            // Automation Date value.
            // into DateTime format
            // using FromOADate() method
            DateTime date2 = DateTime.FromOADate(657435.0);

            // Display the date2
            System.Console.WriteLine("DateTime "
                       + ": {0:y} {0:dd}",date2);

        }

        catch (ArgumentException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
DateTime : 3699 December 28

```

**示例 2:** 适用于*参数异常*

```cs
// C# program to demonstrate the
// DateTime.FromOADate(Int64) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // converting 657435.0 OLE
            // Automation Date value.
            // into DateTime format
            // using FromOADate() method
            DateTime date2 = DateTime.FromOADate(-657435.0);

            // Display the date2
            System.Console.WriteLine("DateTime "
                      + ": {0:y} {0:dd}",date2);

        }

        catch (ArgumentException e) 
        {
            Console.WriteLine("The date is not a valid "+
                           "OLE Automation Date value.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
The date is not a valid OLE Automation Date value.
Exception Thrown: System.ArgumentException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . from oad ate？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.fromoadate?view=netframework-4.7.2)