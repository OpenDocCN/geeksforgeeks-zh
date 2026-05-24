# DateTimeOffset.EqualsExact() 方法在 C# 中的应用

> 原文：[https://www.geeksforgeeks.org/datetimeoffset-equalsexact-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-equalsexact-method-in-c-sharp/)

## 方法介绍

`DateTimeOffset.EqualsExact(DateTimeOffset)` 方法用于确定当前的 `DateTimeOffset` 对象是否表示与指定的 `DateTimeOffset` 对象完全相同的时间，并且具有相同的偏移量。

## 语法与返回值

**语法：**
```csharp
public bool EqualsExact(DateTimeOffset other);
```
这里，`other` 是与当前 `DateTimeOffset` 对象进行比较的对象。

**返回值：**
如果当前 `DateTimeOffset` 对象和 `other` 具有相同的日期时间值和相同的偏移值，则该方法返回 `true`；否则，返回 `false`。

## 示例

以下程序说明了 `DateTimeOffset.EqualsExact(DateTimeOffset)` 方法的使用：

### 示例 1

```csharp
// C# program to demonstrate the
// DateTimeOffset.EqualsExact(DateTimeOffset)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating object of DateTimeOffset
        DateTimeOffset offset1 = new DateTimeOffset(2007,
                 6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

        // creating object of DateTimeOffset
        DateTimeOffset offset2 = new DateTimeOffset(2006,
                 6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

        // comparing two offset1 and offset2
        // instance using EqualsExact() method
        bool value = offset1.EqualsExact(offset2);

        if (value)
        {
            Console.Write("offset1 is same as offset2 ");
        }
        else
        {
            Console.Write("offset1 is not same as offset2");
        }
    }
}
```

**输出：**
```csharp
offset1 is not same as offset2
```

### 示例 2

```csharp
// C# program to demonstrate the
// DateTimeOffset.EqualsExact(DateTimeOffset)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating object of DateTimeOffset
        DateTimeOffset offset1 = new DateTimeOffset(2006,
                 6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

        // creating object of DateTimeOffset
        DateTimeOffset offset2 = new DateTimeOffset(2006,
                 6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

        // comparing two offset1 and offset2
        // instance using EqualsExact() method
        bool value = offset1.EqualsExact(offset2);

        if (value)
        {
            Console.Write("offset1 is same as offset2 ");
        }
        else
        {
            Console.Write("offset1 is not same as offset2");
        }
    }
}
```

**输出：**
```csharp
offset1 is same as offset2
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.equalsexact?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetimeoffset.equalsexact?view=netframework-4.7.2)