# DateTime.ToUniversalTime() 方法在 C# 中

> 原文：[https://www.geeksforgeeks.org/datetime-touniversaltime-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-touniversaltime-method-in-c-sharp/)

此方法用于将当前 `DateTime` 对象的值转换为协调世界时（UTC）。

## 语法

```cs
public DateTime ToUniversalTime();
```

## 返回值

此方法返回一个 `Kind` 属性为 `Utc` 的对象，其值为与当前 `DateTime` 对象的值相等的 UTC 时间。如果转换后的值太大而无法用 `DateTime` 对象表示，则返回 `MaxValue`；如果转换后的值太小而无法用 `DateTime` 对象表示，则返回 `MinValue`。

## 示例

以下程序说明了 `DateTime.ToUniversalTime()` 方法的使用：

### 例 1

```cs
// C# program to demonstrate the
// DateTime.ToUniversalTime()
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating object of DateTime
        DateTime date = new DateTime(2010, 1,
                                1, 4, 0, 15);

        // getting UTC from DateTime
        // using ToUniversalTime() method;
        DateTime value = date.ToUniversalTime();

        // Display the ShortTime
        Console.WriteLine("UTC is {0}", value);
    }
}
```

**输出：**

```cs
UTC is 01/01/2010 04:00:15
```

### 例 2

```cs
// C# program to demonstrate the
// DateTime.ToUniversalTime()
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
        // getting UTC from DateTime
        // using ToUniversalTime() method;
        DateTime value = date.ToUniversalTime();

        // Display the ShortTime
        Console.WriteLine("UTC of {0} is {1}",
                                 date, value);
    }
}
```

**输出：**

```cs
UTC of 01/03/2010 04:00:15 is 01/03/2010 04:00:15
UTC of 01/05/2010 04:00:15 is 01/05/2010 04:00:15
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetime.touniversaltime?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.touniversaltime?view=netframework-4.7.2)