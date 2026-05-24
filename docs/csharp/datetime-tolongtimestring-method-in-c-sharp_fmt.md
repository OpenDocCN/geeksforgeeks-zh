# DateTime.ToLongTimeString() 方法在 C# 中

> 原文：[https://www.geeksforgeeks.org/datetime-tolongtimestring-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-tolongtimestring-method-in-c-sharp/)

## 方法描述

此方法用于将当前 `DateTime` 对象的值转换为其等效的长时间字符串表示形式。

## 语法

```cs
public string ToLongTimeString();
```

## 返回值

此方法返回一个包含当前 `DateTime` 对象的长时间字符串表示的 `string`。

## 示例

以下程序说明了 `DateTime.ToLongTimeString()` 方法的使用：

### 例 1

```cs
// C# program to demonstrate the
// DateTime.ToLongTimeString()
// Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {

// creating object of DateTime
        DateTime date = new DateTime(2011, 1,
                                1, 4, 0, 15);

// Converting the value of the 
        // current DateTime object to 
        // its equivalent long time 
        // string representation.
        // using ToLongTimeString() method;
        string value = date.ToLongTimeString();

// Display the time
        Console.WriteLine("String representation of"+
                              " time is {0}", value);
    }
}
```

**输出：**

```cs
String representation of time is 04:00:15
```

### 例 2

```cs
// C# program to demonstrate the
// DateTime.ToLongTimeString()
// Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {

// creating object of DateTime
        DateTime date = DateTime.Now;

// Converting the value of the
        // current DateTime object to 
        // its equivalent long time 
        // string representation.
        // using ToLongTimeString() method;
        string value = date.ToLongTimeString();

// Display the time
        Console.WriteLine("String representation "+
                          "of time is {0}", value);
    }
}
```

**输出：**

```cs
String representation of time is 05:30:08
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetime.tolongtimestring?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.tolongtimestring?view=netframework-4.7.2)