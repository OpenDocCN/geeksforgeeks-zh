# DateTime.SpecifyKind 方法在 C# 中的使用

> 原文：[https://www.geeksforgeeks.org/datetime-specifykind-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-specifykind-method-in-c-sharp/)

此方法用于创建一个新的 `DateTime` 对象，该对象具有与指定 `DateTime` 相同的刻度数，但被指定为本地时间、协调世界时 (UTC) 或两者都不是，如指定的 `DateTimeKind` 值所示。

## 语法
```csharp
public static DateTime SpecifyKind(DateTime value, DateTimeKind kind);
```

## 参数
- **`value`**: 类型为 `DateTime`，表示日期和时间。
- **`kind`**: 类型为 `DateTimeKind`，是枚举值之一，表示新对象是表示当地时间、世界协调时，还是两者都不表示。

## 返回值
该方法返回一个新 `DateTime` 对象，该对象的刻度数与 `value` 参数表示的对象相同，且其 `Kind` 属性被设置为 `kind` 参数指定的 `DateTimeKind` 值。

## 示例

以下程序说明了 `DateTime.SpecifyKind(DateTime, DateTimeKind)` 方法的使用：

### 例 1
```csharp
// C# program to demonstrate the
// DateTime.SpecifyKind(DateTime,
// DateTimeKind) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating object of DateTime
        DateTime date = new DateTime(2005, 5,
                            6, 14, 34, 42);

        Console.WriteLine("Kind Before Using Method: "
                            + date.Kind);

        // getting DateTime of same DateTime 
        // instance using SpecifyKind() method
        DateTime value = DateTime.SpecifyKind(date,
                            DateTimeKind.Local);

        Console.WriteLine("Kind After Using Method: " +
                            value.Kind);

        Console.WriteLine("DateTime is {0}", value);
    }
}
```

**输出：**
```csharp
Kind Before Using Method: Unspecified
Kind After Using Method: Local
DateTime is 05/06/2005 14:34:42
```

### 例 2
```csharp
// C# program to demonstrate the
// DateTime.SpecifyKind(DateTime,
// DateTimeKind) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating object of DateTime
        DateTime date = new DateTime(1970, 1,
                            1, 4, 0, 15);

        // getting DateTime of same DateTime 
        // instance using SpecifyKind() method
        DateTime value = DateTime.SpecifyKind(date,
                            DateTimeKind.Local);

        Console.WriteLine("DateTime is {0}", value);
    }
}
```

**输出：**
```csharp
DateTime is 01/01/1970 04:00:15
```

## 参考
*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetime.specifykind?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.specifykind?view=netframework-4.7.2)