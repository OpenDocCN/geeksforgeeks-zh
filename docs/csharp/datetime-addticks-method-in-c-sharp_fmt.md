# DateTime.AddTicks() 方法

> 原文：[https://www.geeksforgeeks.org/datetime-addticks-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-addticks-method-in-c-sharp/)

此方法用于返回新的 `DateTime`，该 `DateTime` 将指定数量的刻度添加到此实例的值中。此方法不更改此 `DateTime` 的值。相反，它返回一个新的 `DateTime`，其值是此操作的结果。

## 语法

```cs
public DateTime AddTicks (long value);
```

这里，它需要 100 纳秒的节拍数。

## 返回值

此方法返回一个对象，该对象的值是此实例表示的日期和时间与 `value` 表示的时间之和。

## 异常

如果生成的 `DateTime` 小于 `MinValue` 或大于 `MaxValue`，此方法将给出 `ArgumentOutOfRangeException`。

以下程序说明了 `DateTime.AddTicks(Int64)` 方法的使用：

### 例 1

```cs
// C# program to demonstrate the
// DateTime.AddTicks(Double) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of DateTime
            DateTime date1 = new DateTime(2010, 1, 
                                     1, 4, 0, 15);

            // adding the 3000 ticks
            // using AddTicks() method;
            DateTime date2 = date1.AddTicks(3000);

            // Display the date1
            Console.WriteLine("No. of ticks before operation: "
                                        + "{0}", date1.Ticks);

            // Display the date2
            Console.WriteLine("\nNo. of ticks after operation: "
                                         + "{0}",  date2.Ticks);

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
No. of ticks before operation: 633979152150000000

No. of ticks after operation: 633979152150003000
```

### 例 2：为 `ArgumentOutOfRangeException`

```cs
// C# program to demonstrate the
// DateTime.AddTicks(long) Method
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
                                    + "{0}", date1.Ticks);

            // adding the 1 Ticks
            // using AddTicks() method;
            DateTime date2 = date1.AddTicks(1);

            // Display the date2
            Console.WriteLine("\nDateTime after operation: "
                                      + "{0}",  date2.Ticks);

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
DateTime before operation: 3155378975999999999

The resulting DateTime is greater than the DateTime.MaxValue 
Exception Thrown: System.ArgumentOutOfRangeException
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetime.addticks?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.addticks?view=netframework-4.7.2)