# DateTime.ToOADate() 方法在 C# 中

> 原文：[https://www.geeksforgeeks.org/datetime-tooadate-method-in-c-sharp/](https://www.geeksforgeeks.org/datetime-tooadate-method-in-c-sharp/)

## 方法描述
此方法用于将此实例的值转换为等效的 OLE 自动化日期。

## 语法
```cs
public double ToOADate();
```

## 返回值
此方法返回一个 `double` 浮点数，其中包含一个与此实例值相等的 OLE 自动化日期。

## 异常
- **OverflowException**：如果此实例的值不能表示为 OLE 自动化日期。

## 示例
以下程序说明了 `DateTime.ToOADate()` 方法的使用。

### 示例 1
```cs
// C# program to demonstrate the
// DateTime.ToOADate() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of DateTime
            DateTime date = new DateTime(2011, 1,
                                         1, 4, 0, 15);

            // Converts the value of this instance to
            // the equivalent OLE Automation date.
            // using ToOADate() method;
            double value = date.ToOADate();

            // Display the time
            Console.WriteLine("OLE Automation date is {0}", value);
        }

        catch (OverflowException e) {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```
**输出：**
```cs
OLE Automation date is 40544.1668402778
```

### 示例 2：适用于 OverflowException
```cs
// C# program to demonstrate the
// DateTime.ToOADate() Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // creating object of DateTime
            DateTime date = new DateTime(0099, 1,
                                         1, 4, 0, 15);

            // Converts the value of this instance 
            // to the equivalent OLE Automation date.
            // using ToOADate() method;
            double value = date.ToOADate();

            // Display the time
            Console.WriteLine("OLE Automation date is {0}", value);
        }

        catch (OverflowException e)
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```
**输出：**
```cs
Exception Thrown: System.OverflowException
```

## 参考
*   [https://docs.microsoft.com/en-us/dotnet/api/system.datetime.tooadate?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.tooadate?view=netframework-4.7.2)