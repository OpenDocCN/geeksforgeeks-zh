# DateTimeOffset.GetHashCode Method in C#

> 原文:[https://www . geesforgeks . org/datetime offset-gethashcode-method-in-c-sharp/](https://www.geeksforgeeks.org/datetimeoffset-gethashcode-method-in-c-sharp/)

**DateTimeOffset。GetHashCode 方法**用于获取当前 DateTimeOffset 对象的哈希代码。

> **语法:**public override int GetHashCode()；
> 
> **返回值:**这个方法返回一个 32 位有符号整数哈希码。

以下程序说明了**日期时间偏移的使用。GetHashCode()** 方法:

**例 1:**

```cs
// C# program to demonstrate the
// DateTimeOffset.GetHashCode()
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        // creating object of  DateTimeOffset
        DateTimeOffset offset = new DateTimeOffset(2007,
                6, 1, 7, 55, 0, new TimeSpan(-5, 0, 0));

        // Returns the hash code for the
        // current DateTimeOffset object.
        // instance using GetHashCode() method
        int value = offset.GetHashCode();

        // Display the HashCode
        Console.WriteLine("HashCode for DateTimeOffset is: {0}", value);
    }
}
```

**Output:**

```cs
HashCode for DateTimeOffset is: 981031011

```

**例 2:**

```cs
// C# program to demonstrate the
// DateTimeOffset.GetHashCode()
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() Method
        get(new DateTimeOffset(2007, 6, 1, 7, 
             55, 0, new TimeSpan(-5, 0, 0)));

        get(new DateTimeOffset(2017, 6, 1, 7,
             55, 0, new TimeSpan(-5, 0, 0)));
    }
    public static void get(DateTimeOffset offset)
    {

        // Returns the hash code for the 
        // current DateTimeOffset object.
        // instance using GetHashCode() method
        int value = offset.GetHashCode();

        // Display the HashCode
        Console.WriteLine("HashCode for DateTimeOffset is: {0}", value);
    }
}
```

**Output:**

```cs
HashCode for DateTimeOffset is: 981031011
HashCode for DateTimeOffset is: 1633960685

```