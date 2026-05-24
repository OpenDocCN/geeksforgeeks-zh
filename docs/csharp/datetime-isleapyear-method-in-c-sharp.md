# 日期时间。C# 中的 IsLeapYear()方法

> 原文:[https://www . geesforgeks . org/datetime-islapyear-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-isleapyear-method-in-c-sharp/)

此方法返回指定年份是否为闰年的指示。在这里，年份总是被解释为公历中的一年。

**语法:**

```cs
public static bool IsLeapYear (int year);
```

**返回值:**如果年份是闰年，这个方法返回*真*，否则返回*假*。

**异常:**如果*年*小于 1 *或*大于 9999，此方法将给出*argumentout of range Exception*。

以下程序说明了上述方法的使用:

**例 1:**

## C#

```cs
// C# code to demonstrate the
// IsLeapYear(Int32) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Checking the leap year between 2000 to 2019
        for (int y = 2000; y <= 2019; y++)
        {

            // using method
            if (DateTime.IsLeapYear(y))
            {
                Console.WriteLine("{0} is a Leap Year.", y);
            }

            else
            {
                Console.WriteLine("{0} is not a Leap Year.", y);
            }
        }
    }
}
```

**输出:**

```cs
2000 is a Leap Year.
2001 is not a Leap Year.
2002 is not a Leap Year.
2003 is not a Leap Year.
2004 is a Leap Year.
2005 is not a Leap Year.
2006 is not a Leap Year.
2007 is not a Leap Year.
2008 is a Leap Year.
2009 is not a Leap Year.
2010 is not a Leap Year.
2011 is not a Leap Year.
2012 is a Leap Year.
2013 is not a Leap Year.
2014 is not a Leap Year.
2015 is not a Leap Year.
2016 is a Leap Year.
2017 is not a Leap Year.
2018 is not a Leap Year.
2019 is not a Leap Year.
```

**例 2:**

## C#

```cs
// C# code to demonstrate the
// IsLeapYear(Int32) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // using method
        if (DateTime.IsLeapYear(9999))
        {
            Console.WriteLine("9999 is a Leap Year.");
        }

        else
        {
            Console.WriteLine("9999 is not a Leap Year.");
        }

        // using method will give an error
        // as year's value is greater than
        // 9999
        if (DateTime.IsLeapYear(10000))
        {
            Console.WriteLine(" 10000 is a Leap Year.");
        }

        else {
            Console.WriteLine("10000 is not a Leap Year.");
        }
    }
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:年份必须介于 1 和 9999 之间。
> 参数名称:年份

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . islapy ear？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.isleapyear?view=netframework-4.7.2)