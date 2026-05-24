# DateTime.AddMilliseconds() 方法在 C# 中

> 原文：[https://www.geeksforgeeks.org/datetime-addmilliseconds-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-addmilliseconds-method-in-c-sharp/)

此方法用于返回一个新的 `DateTime`，该对象的值是将指定的毫秒数添加到当前实例的值中。

## 语法

```cs
public DateTime AddMilliseconds (double value);
```

这里，它接受整数和小数毫秒。`value` 参数可以是负数或正数，并四舍五入到最接近的整数。

## 返回值

该方法返回一个对象，该对象的值是该实例表示的日期和时间与 `value` 表示的毫秒数之和。

## 异常

如果结果 `DateTime` 小于 `DateTime.MinValue` 或大于 `DateTime.MaxValue`，此方法将抛出 `ArgumentOutOfRangeException`。

以下程序说明了 `DateTime.AddMilliseconds(double)` 方法的使用：

## 示例 1

```cs
// C# program to demonstrate the
// DateTime.AddMilliseconds() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of DateTime
            DateTime date1 = new DateTime(2010, 1, 1,
                                           4, 0, 15);

            // adding the 3000 Milliseconds
            // using AddMilliseconds() method;
            DateTime date2 = date1.AddMilliseconds(3000);

            // Display the date1
            Console.WriteLine("DateTime before operation: "
                           + "{0:hh}:{0:mm}:{0:ss}", date1);

            // Display the date2
            Console.WriteLine("\nDateTime after operation: "
                           + "{0:hh}:{0:mm}:{0:ss}", date2);

        }
        catch (ArgumentOutOfRangeException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出：**

```cs
DateTime before operation: 04:00:15

DateTime after operation: 04:00:18
```

## 示例 2：为 `ArgumentOutOfRangeException`

```cs
// C# program to demonstrate the
// DateTime.AddMilliseconds() Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of DateTime 
            // and initialize with MinValue
            DateTime date1 = DateTime.MaxValue;

            // Display the date1
            Console.WriteLine("DateTime before operation: "
                                     + "{0}", date1);

            // adding the 3000 Milliseconds
            // using AddHours() method;
            DateTime date2 = date1.AddHours(3000);

            // Display the date2
            Console.WriteLine("\nDateTime after operation: "
                           + "{0:hh}:{0:mm}:{0:ss}", date2);

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

**输出：**

```cs
DateTime before operation: 12/31/9999 23:59:59

The resulting DateTime is greater than the DateTime.MaxValue 
Exception Thrown: System.ArgumentOutOfRangeException
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetime.addmilliseconds?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.addmilliseconds?view=netframework-4.7.2)