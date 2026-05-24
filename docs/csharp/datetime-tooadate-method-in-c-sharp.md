# 日期时间。C# 中的 ToOADate()方法

> 原文:[https://www . geesforgeks . org/datetime-tooadate-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-tooadate-method-in-c-sharp/)

此方法用于将此实例的值转换为等效的 OLE 自动化日期。

> **语法:**公共双 ToOADate()；
> 
> **返回值:**此方法返回一个双精度浮点数，其中包含一个与此实例值相等的 OLE 自动化日期。
> 
> **异常:**
> **飞越异常:**如果此实例的值不能表示为 OLE 自动化日期。

以下程序说明了**日期时间的使用。**方法

**例 1:**

```cs
// C# program to demonstrate the
// DateTime.ToOADate() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of DateTime
            DateTime date = new DateTime(2011, 1,
                                     1, 4, 0, 15);

            // Converts the value of this instance to
            // the equivalent OLE Automation date.
            // using ToOADate() method;
            double value = date.ToOADate();

            // Display the time
            Console.WriteLine("OLE Automation date is {0}", value);
        }

        catch (OverflowException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
OLE Automation date is 40544.1668402778

```

**例 2:** 适用于*飞越异常*

```cs
// C# program to demonstrate the
// DateTime.ToOADate() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of DateTime
            DateTime date = new DateTime(0099, 1,
                                         1, 4, 0, 15);

            // Converts the value of this instance 
            // to the equivalent OLE Automation date.
            // using ToOADate() method;
            double value = date.ToOADate();

            // Display the time
            Console.WriteLine("OLE Automation date is {0}", value);
        }

        catch (OverflowException e)
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
Exception Thrown: System.OverflowException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . tooadate？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.tooadate?view=netframework-4.7.2)