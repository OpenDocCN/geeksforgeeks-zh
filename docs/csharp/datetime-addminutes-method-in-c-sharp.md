# 日期时间。C# 中的 AddMinutes()方法

> 原文:[https://www . geesforgeks . org/datetime-add minutes-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-addminutes-method-in-c-sharp/)

此方法用于返回一个新的日期时间，该日期时间将指定的分钟数添加到此实例的值中。

**语法:**

```cs
public DateTime AddMinutes (double value);
```

这里，*值*是整数和分数分钟的数字。*值*参数可以是负数或正数。

**返回值:**该方法返回一个对象，该对象的值是该实例表示的日期和时间与*值*表示的分钟数之和。

**异常:**如果结果日期时间小于*最小值*或大于*最大值*，此方法将抛出*argumentout of range Exception*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to demonstrate the
// DateTime.AddMinutes(Double) Method
using System;

class GFG {

// Main Method
public static void Main()
{

    // Creating a DateTime object
    DateTime d1 = new DateTime(2018, 9,
                            7, 7, 0, 0);

    // Taking minutes
    double[] m1 = {.01567, .06743, 12.12347,
                           .89, .6666, 250.0};

    foreach(double m2 in m1)
    {

        // using the method
        Console.WriteLine("{0} + {1} minute(s) = {2}", d1,
                                   m2, d1.AddMinutes(m2));
    }                    
}
}
```

**输出:**

```cs
09/07/2018 07:00:00 + 0.01567 minute(s) = 09/07/2018 07:00:00
09/07/2018 07:00:00 + 0.06743 minute(s) = 09/07/2018 07:00:04
09/07/2018 07:00:00 + 12.12347 minute(s) = 09/07/2018 07:12:07
09/07/2018 07:00:00 + 0.89 minute(s) = 09/07/2018 07:00:53
09/07/2018 07:00:00 + 0.6666 minute(s) = 09/07/2018 07:00:39
09/07/2018 07:00:00 + 250 minute(s) = 09/07/2018 11:10:00

```

**例 2:**

```cs
// C# program to demonstrate the
// DateTime.AddMinutes(Double) Method
using System;

class GFG {

// Main Method
public static void Main()
{

    // Creating a DateTime object
    // by taking it MaxValue
    DateTime d1 = DateTime.MaxValue;

    // Taking minute variable
    double m1 = 1.7;

    // Using the Method will error as the
    // resulting DateTime is greater than 
    // MaxValue
    Console.WriteLine(d1.AddMinutes(m1));
}
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:相加或相减的值导致不可表示的日期时间。
> 参数名称:值

**注:**

*   此方法不更改此日期时间的值。相反，它返回一个新的日期时间，其值是此操作的结果。
*   *值的小数部分*是一分钟的小数部分。例如，7.5 相当于 7 分钟、30 秒、0 毫秒和 0 刻度。
*   *值*参数四舍五入到最接近的毫秒。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . add minutes？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.addminutes?view=netframework-4.7.2)