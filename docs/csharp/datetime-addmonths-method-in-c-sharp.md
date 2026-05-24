# 日期时间。C# 中的 AddMonths()方法

> 原文:[https://www . geesforgeks . org/datetime-add months-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-addmonths-method-in-c-sharp/)

此方法用于返回一个新的日期时间，该日期时间将指定的月数添加到此实例的值中。

**语法:**

```cs
public DateTime AddMonths (int months);
```

这里，*个月*是月数。*月份*参数可以是负数或正数。

**返回值:**该方法返回一个对象，该对象的值是该实例表示的日期和时间与*月份*之和。

**异常:**如果结果日期时间小于最小值或大于最大值 `or` *个月*小于-120，000 或大于 120，000，此方法将抛出*argumentout of range Exception*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to demonstrate the
// DateTime.AddMonths(Int32) Method
using System;

class GFG {

// Main Method
public static void Main()
{

    // Creating a DateTime object
    DateTime d1 = new DateTime(2018, 4, 17);

    for (int i = 0; i <= 10; i++)
    {

        // using the method
        Console.WriteLine(d1.AddMonths(i).ToString("d"));

    }

    Console.WriteLine("In Leap Years:");

    // Creating a DateTime object
    // by taking a leap year
    // It is 31st March 2016
    DateTime d2 = new DateTime(2016, 03, 31);

    // taking a month value
    int m = 1;

    // using the method
    // Result will be 30 April 2016
    Console.WriteLine(d2.AddMonths(m).ToString("d"));

}
}
```

**输出:**

```cs
04/17/2018
05/17/2018
06/17/2018
07/17/2018
08/17/2018
09/17/2018
10/17/2018
11/17/2018
12/17/2018
01/17/2019
02/17/2019
In Leap Years:
04/30/2016

```

**例 2:**

```cs
// C# program to demonstrate the
// DateTime.AddMonths(Int32) Method
using System;

class GFG {

// Main Method
public static void Main()
{

    // Creating a DateTime object
    // taking MaxValue
    DateTime d1 = DateTime.MaxValue;

    // taking a month MaxValue
    int m = 12005;

    // using the method will 
    // give an runtime error
    // as months parameter is
    // greater than 12000
    Console.WriteLine(d1.AddMonths(m).ToString("d"));
}
}
```

**运行时错误:**

> 未处理异常:
> 系统。ArgumentOutOfRangeException:相加或相减的值导致不可表示的日期时间。
> 参数名称:月

**注:**

*   此方法不更改此日期时间对象的值。相反，它返回一个新的 DateTime 对象，其值是此操作的结果。
*   这会计算结果月份和年份，考虑闰年和一个月中的天数，然后调整结果日期时间对象的日期部分。
*   结果日期时间对象的时间部分与此实例保持不变。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . datetime . add months？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.addmonths?view=netframework-4.7.2)