# DateTime.GetHashCode() 方法 in C#

> 原文: [https://www.geeksforgeeks.org/datetime-gethashcode-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-gethashcode-method-in-c-sharp/)

此方法用于返回此实例的哈希代码。

## 语法

```cs
public override int GetHashCode();
```

## 返回值

这个方法返回一个 32 位有符号整数哈希码。

## 示例

以下程序说明了 `DateTime.GetHashCode()` 方法的使用：

### 示例 1

```cs
// C# program to demonstrate the
// DateTime.GetHashCode()
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // creating object of DateTime
        DateTime date = new DateTime(2010, 1,
                                 1, 4, 0, 15);

        // getting hashcode from DateTime
        // using GetHashCode() method;
        int value = date.GetHashCode();

        // Display the hashcode
        Console.WriteLine("hashcode is {0}", value);
    }
}
```

**输出:**

```cs
hashcode is 103491886
```

### 示例 2

```cs
// C# program to demonstrate the
// DateTime.GetHashCode()
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
        // getting HashCode from DateTime
        // using GetHashCode() method;
        int value = date.GetHashCode();

        // Display the ShortTime
        Console.WriteLine("HashCode of {0} is {1}",
                                     date, value);
    }
}
```

**输出:**

```cs
HashCode of 01/03/2010 04:00:15 is 1802939328
HashCode of 01/05/2010 04:00:15 is -1337841070
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetime.gethashcode?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.gethashcode?view=netframework-4.7.2)