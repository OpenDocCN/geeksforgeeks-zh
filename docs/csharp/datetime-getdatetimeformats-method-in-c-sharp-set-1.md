# 日期时间。C# 中的 GetDateTimeFormats()方法| Set–1

> 原文:[https://www . geesforgeks . org/datetime-getdatetime formats-method-in-c-sharp-set-1/](https://www.geeksforgeeks.org/datetime-getdatetimeformats-method-in-c-sharp-set-1/)

此方法用于将此实例的值转换为标准日期和时间格式说明符支持的所有字符串表示形式。该方法的重载列表中总共有 4 个方法:

*   **GetDateTimeFormats（）**
*   **get data time format(char)**
*   **日期时间格式(格式提供者)**
*   **日期时间格式(Char，格式提供者)**

#### GetDateTimeFormats()

此方法用于将此实例的值转换为标准日期和时间格式说明符支持的所有字符串表示形式。

> **语法:**公共字符串[] GetDateTimeFormats()
> 
> **返回值:**此方法返回一个字符串数组，其中每个元素都是用标准日期和时间格式说明符之一格式化的此实例的值的表示。

以下程序说明了 *GetDateTimeFormats()* 方法的使用:

**例 1:**

```cs
// C# program to demonstrate the
// DateTime.GetDateTimeFormats()
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating object of DateTime
        DateTime date = new DateTime(2010, 1,
                                     1, 4, 0, 15);

        // getting format in string array
        // using GetDateTimeFormats() method;
        string[] value = date.GetDateTimeFormats();

        // Print out value in all DateTime 
        // formats using the default culture.
        foreach(string format in value)
            Console.WriteLine(format);
    }
}
```

**Output:**

```cs
01/01/2010
2010-01-01
Friday, 01 January 2010
Friday, 01 January 2010 04:00
Friday, 01 January 2010 04:00 AM
Friday, 01 January 2010 4:00
Friday, 01 January 2010 4:00 AM
Friday, 01 January 2010 04:00:15
01/01/2010 04:00
01/01/2010 04:00 AM
01/01/2010 4:00
01/01/2010 4:00 AM
2010-01-01 04:00
2010-01-01 04:00 AM
2010-01-01 4:00
2010-01-01 4:00 AM
01/01/2010 04:00:15
2010-01-01 04:00:15
January 01
January 01
2010-01-01T04:00:15.0000000
2010-01-01T04:00:15.0000000
Fri, 01 Jan 2010 04:00:15 GMT
Fri, 01 Jan 2010 04:00:15 GMT
2010-01-01T04:00:15
04:00
04:00 AM
4:00
4:00 AM
04:00:15
2010-01-01 04:00:15Z
Friday, 01 January 2010 04:00:15
2010 January
2010 January

```

**例 2:**

```cs
// C# program to demonstrate the
// DateTime.GetDateTimeFormats()
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating object of DateTime
        DateTime date = new DateTime(2019, 1,
                              30, 9, 49, 15);

        // getting format in string array
        // using GetDateTimeFormats() method;
        string[] value = date.GetDateTimeFormats();

        // Print out value in all DateTime 
        // formats using the default culture.
        for (int i = 1; i <= 6; i++)
            Console.WriteLine(value[i]);
    }
}
```

**Output:**

```cs
2019-01-30
Wednesday, 30 January 2019
Wednesday, 30 January 2019 09:49
Wednesday, 30 January 2019 09:49 AM
Wednesday, 30 January 2019 9:49
Wednesday, 30 January 2019 9:49 AM

```

#### 日期时间格式(Char)

此方法用于将此实例的值转换为指定的标准日期和时间格式说明符支持的所有字符串表示形式。

> **语法:**公共字符串[] GetDateTimeFormats (char 格式)；
> 这里需要一个标准的日期和时间格式字符串。
> 
> **返回值:**这个方法返回一个字符串数组，其中每个元素都是用格式标准日期和时间格式说明符格式化的这个实例的值的表示。
> 
> **异常:**如果*格式*不是有效的标准日期和时间格式说明符，此方法将给出*格式异常*。

以下程序说明了*获取日期时间格式(字符)*方法的使用:

**例 1:**

```cs
// C# program to demonstrate the
// DateTime.GetDateTimeFormats(Char)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {
            // creating object of DateTime
            DateTime date = new DateTime(2010, 1,
                                     1, 4, 0, 15);

            // Get the long date formats using the current
            // culture. using GetDateTimeFormats() method
            string[] value = date.GetDateTimeFormats('D');

            // Print out value in all DateTime
            // formats using the default culture.
            foreach(string format in value)
                Console.WriteLine(format);
        }
        catch (FormatException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
Friday, 01 January 2010

```

**例 2:** 为*格式异常*

```cs
// C# program to demonstrate the
// DateTime.GetDateTimeFormats(Char)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {
            // creating object of DateTime
            DateTime date = new DateTime(2010, 1,
                                         1, 4, 0, 15);

            // Get the date format
            // using GetDateTimeFormats(Char) method;
            string[] value = date.GetDateTimeFormats('X');

            // Print out value in all DateTime 
            // formats using the default culture.
            foreach(string format in value)
                Console.WriteLine(format);
        }
        catch (FormatException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
Exception Thrown: System.FormatException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . getdatetime formats？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.getdatetimeformats?view=netframework-4.7.2)