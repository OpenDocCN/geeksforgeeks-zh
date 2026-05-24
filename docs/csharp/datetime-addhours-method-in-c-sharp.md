# 日期时间。C# 中的 AddHours()方法

> 原文:[https://www . geesforgeks . org/datetime-addhours-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-addhours-method-in-c-sharp/)

此方法用于返回一个新的日期时间，该日期时间将指定的小时数添加到此实例的值中。

**语法:**

```cs
public DateTime AddHours (double value);
```

这里*值*是整数和小数的小时数。*值*参数可以是负数或正数。

**返回值:**该方法返回一个对象，该对象的值是该实例表示的日期和时间与*值*表示的小时数之和。

**异常:**如果生成的日期时间小于*最小值*或大于*最大值*，此方法将给出*argumentout of range Exception*。

以下程序说明了*日期时间的使用。添加天数(双倍)*方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTime.AddHours(Double) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of DateTime
            DateTime date1 = new DateTime(2010, 1,
                                     1, 4, 0, 15);

            // adding the 5.50 hours
            // using AddHours() method;
            DateTime date2 = date1.AddHours(5.50);

            // Display the date1
            Console.WriteLine("DateTime before operation:"+
                            " {0:y} {0:dd}, {0:t}", date1);

            // Display the date2
            Console.WriteLine("\nDateTime after operation: "+
                               "{0:y} {0:dd}, {0:t}", date2);
        }

        catch (ArgumentOutOfRangeException e)
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
DateTime before operation: 2010 January 01, 04:00

DateTime after operation: 2010 January 01, 09:30

```

**例 2:** 为*argumentout of range exception*

```cs
// C# program to demonstrate the
// DateTime.AddHours(Double) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of DateTime 
            // and initialize with MinValue
            DateTime date1 = DateTime.MaxValue;

            // Display the date1
            Console.WriteLine("DateTime before operation: "+
                              "{0:y} {0:dd}, {0:t}", date1);

            // adding the TimeSpan of 5 days
            // using AddHours() method;
            DateTime date2 = date1.AddHours(5);

            // Display the date2
            System.Console.WriteLine("\nDateTime after operation:"+
                                    " {0:y} {0:dd}, {0:t}", date2);
        }

        catch (ArgumentOutOfRangeException e) 
        {
            Console.WriteLine("\nThe resulting DateTime is "+
                      "greater than the DateTime.MaxValue ");

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
DateTime before operation: 9999 December 31, 23:59

The resulting DateTime is greater than the DateTime.MaxValue 
Exception Thrown: System.ArgumentOutOfRangeException

```

**注:**

*   此方法不更改此日期时间的值。相反，它返回一个新的日期时间，其值是此操作的结果。
*   *值的小数部分*是一分钟的小数部分。例如，7.5 相当于 7 分钟、30 秒、0 毫秒和 0 刻度。
*   *值*参数四舍五入到最接近的毫秒。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . addhours？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.addhours?view=netframework-4.7.2)