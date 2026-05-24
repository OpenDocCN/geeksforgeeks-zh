# DateTime.AddMonths() 方法在 C# 中

> 原文：[https://www.geeksforgeeks.org/datetime-addmonths-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-addmonths-method-in-c-sharp/)

此方法用于返回一个新的 `DateTime`，该对象的值是将指定的月数添加到当前实例的值之后的结果。

## 语法

```cs
public DateTime AddMonths (int months);
```

这里，`months` 是要添加的月数。`months` 参数可以是负数或正数。

## 返回值

该方法返回一个 `DateTime` 对象，其值是此实例表示的日期和时间与 `months` 参数之和。

## 异常

如果结果 `DateTime` 小于 `DateTime.MinValue` 或大于 `DateTime.MaxValue`，或者 `months` 小于 -120,000 或大于 120,000，此方法将抛出 `ArgumentOutOfRangeException`。

## 示例

以下程序说明了上述方法的使用：

### 例 1

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

### 输出

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

### 例 2

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

### 运行时错误

> 未处理异常:
> System.ArgumentOutOfRangeException: 相加或相减的值导致不可表示的 DateTime。
> 参数名称: months

## 注

*   此方法不更改此 `DateTime` 对象的值。相反，它返回一个新的 `DateTime` 对象，其值是此操作的结果。
*   这会计算结果月份和年份，考虑闰年和一个月中的天数，然后调整结果 `DateTime` 对象的日期部分。
*   结果 `DateTime` 对象的时间部分与此实例保持不变。

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetime.addmonths?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.addmonths?view=netframework-4.7.2)