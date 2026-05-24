# DateTime.GetTypeCode() 方法（C#）

> 原文：[https://www.geeksforgeeks.org/datetime-gettypecode-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-gettypecode-method-in-c-sharp/)

此方法用于返回 `DateTime` 值类型的类型代码。

> **语法：** `public TypeCode GetTypeCode();`
>
> **返回值：** 该方法返回枚举常量 `DateTime`。

以下程序说明了 `DateTime.GetTypeCode()` 方法的使用。

**例 1：**

```cs
// C# program to demonstrate the
// DateTime.GetTypeCode()
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating object of DateTime
        DateTime date = new DateTime(2010, 1,
                                1, 4, 0, 15);

        // getting Typecode of date
        // using GetTypeCode() method;
        TypeCode value = date.GetTypeCode();

        // Display the hashcode
        Console.WriteLine("TypeCode is {0}", value);
    }
}
```

**Output：**

```cs
TypeCode is DateTime
```

**例 2：**

```cs
// C# program to demonstrate the
// DateTime.GetTypeCode()
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling check() method
        check(new DateTime(2010, 1,
                     3, 4, 0, 15));

        check(new DateTime(2010, 1,
                     5, 4, 0, 15));
    }

    public static void check(DateTime date)
    {
        // getting TypeCode of date
        // using GetTypeCode() method;
        TypeCode value = date.GetTypeCode();

        // Display the ShortTime
        Console.WriteLine("TypeCode of {0} is {1}",
                                     date, value);
    }
}
```

**Output：**

```cs
TypeCode of 01/03/2010 04:00:15 is DateTime
TypeCode of 01/05/2010 04:00:15 is DateTime
```

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetime.gettypecode?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.gettypecode?view=netframework-4.7.2)