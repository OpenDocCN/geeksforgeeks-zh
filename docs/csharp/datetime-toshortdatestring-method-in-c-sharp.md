# 日期时间。C# 中的 ToShortDateString()方法

> 原文:[https://www . geesforgeks . org/datetime-to short datestring-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-toshortdatestring-method-in-c-sharp/)

此方法用于将当前日期时间对象的值转换为其等效的短日期字符串表示形式。

> **语法:**公共字符串 to short date string()；
> 
> **返回值:**该方法返回一个字符串，该字符串包含当前 DateTime 对象的短日期字符串表示形式。

以下程序说明了*日期时间的使用。*方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTime.ToShortDateString()
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of DateTime
            DateTime date = new DateTime(2010, 1,
                                    1, 4, 0, 15);

            // getting ShortTime from DateTime
            // using ToShortDateString() method;
            string value = date.ToShortDateString();

            // Display the ShortTime
            Console.WriteLine("date is {0}", value);
        }

        catch (FormatException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
date is 01/01/2010

```

**例 2:**

```cs
// C# program to demonstrate the
// DateTime.ToShortDateString()
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // calling check() method
        check(new DateTime(2010, 1, 3, 4, 0, 15));

        check(new DateTime(2010, 1, 5, 4, 0, 15));

        check(new DateTime(2010, 1, 5, 4, 0, 15));
    }

    public static void check(DateTime date)
    {

        // getting ShortTime from DateTime
        // using ToShortDateString() method;
        string value = date.ToShortDateString();

        // Display the date
        Console.WriteLine("date of {0} is "+
                        "{1}", date, value);
    }
}
```

**Output:**

```cs
date of 01/03/2010 04:00:15 is 01/03/2010
date of 01/05/2010 04:00:15 is 01/05/2010
date of 01/05/2010 04:00:15 is 01/05/2010

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . toshortdatestring？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.toshortdatestring?view=netframework-4.7.2)