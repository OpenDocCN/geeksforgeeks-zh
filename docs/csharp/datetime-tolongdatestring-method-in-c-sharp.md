# 日期时间。C# 中的 ToLongDateString()方法

> 原文:[https://www . geesforgeks . org/datetime-tolongdatestring-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-tolongdatestring-method-in-c-sharp/)

此方法用于将当前日期时间对象的值转换为其等效的长日期字符串表示形式。

> **语法:**公共字符串 ToLongDateString()；
> 
> **返回值:**这个方法返回一个包含当前 DateTime 对象的长日期字符串表示的字符串。

以下程序说明了**日期时间的使用。ToLongDateString()** 方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTime.ToLongDateString()
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // creating object of DateTime
        DateTime date = new DateTime(2011, 1,
                                1, 4, 0, 15);

        // Converting the value of the 
        // current DateTime object to 
        // its equivalent long date 
        // string representation.
        // using ToLongDateString() method;
        string value = date.ToLongDateString();

        // Display the date
        Console.WriteLine("String representation"+
                        " of date is {0}", value);
    }
}
```

**Output:**

```cs
String representation of date is Saturday, 01 January 2011

```

**例 2:**

```cs
// C# program to demonstrate the
// DateTime.ToLongDateString()
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // creating object of DateTime
        DateTime date = DateTime.Now;

        // Converting the value of the
        // current DateTime object to 
        // its equivalent long date 
        // string representation.
        // using ToLongDateString() method;
        string value = date.ToLongDateString();

        // Display the date
        Console.WriteLine("String representation "+
                          "of date is {0}", value);
    }
}
```

**Output:**

```cs
String representation of date is Monday, 11 February 2019

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . tolongdatestring？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.tolongdatestring?view=netframework-4.7.2)