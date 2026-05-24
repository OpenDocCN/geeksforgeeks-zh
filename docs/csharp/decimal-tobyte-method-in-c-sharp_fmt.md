# Decimal.ToByte() 方法

> 原文：[https://www.geeksforgeeks.org/decimal-tobyte-method-in-c-sharp/](https://www.geeksforgeeks.org/decimal-tobyte-method-in-c-sharp/)

此方法用于将指定的十进制值转换为等效的 8 位无符号整数。

## 语法

```cs
public static byte ToByte(decimal a);
```

## 参数

- `a`：该参数指定将被求反的小数。

## 返回值

将返回一个相当于 `a` 的 8 位无符号整数。

## 异常

如果值即 `a` 小于最小值或大于最大值，该方法将给出`OverflowException`。

下面的程序说明了`Decimal.ToByte(Decimal)`方法的使用：

## 示例 1

```cs
// C# program to demonstrate the
// Decimal.ToByte(Decimal) Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// Declaring the decimal variable
            Decimal a = 127.97m;

// using ToByte() method;
            byte value = Decimal.ToByte(a);

// Display the byte value
            Console.WriteLine("The Byte value "+
                             "is : {0}", value);
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
The Byte value is : 127
```

## 示例 2

```cs
// C# program to demonstrate the
// Decimal.ToByte(Decimal) Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// Declaring the decimal variable
            Decimal a = -0.999m;

// using ToByte() method;
            byte value = Decimal.ToByte(a);

// Display the byte value
            Console.WriteLine("The Byte value"+
                           " is : {0}", value);
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
The Byte value is : 0
```

## 示例 3：`OverflowException` 的程序

```cs
// C# program to demonstrate the
// Decimal.ToByte(Decimal) Method
using System;
using System.Globalization;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// Declaring the decimal variable
            Decimal a = -98.45m;

// using ToByte() method;
            byte value = Decimal.ToByte(a);

// Display the byte value
            Console.WriteLine("The Byte value "+
                             "is : {0}", value);
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

- [https://docs.microsoft.com/en-us/dotnet/api/system.decimal.tobyte?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.tobyte?view=netframework-4.7.2)