# Decimal.Divide() 方法在 C# 中

> 原文：[https://www.geeksforgeeks.org/decimal-divide-method-in-c-sharp/](https://www.geeksforgeeks.org/decimal-divide-method-in-c-sharp/)

此方法用于将两个指定的十进制值相除。

## 语法

```csharp
public static decimal Divide(decimal a1, decimal a2);
```

## 参数

- `a1`：此参数指定被除数。
- `a2`：此参数指定除数。

## 返回值

将 `a1` 除以 `a2` 的结果。

## 异常

- `DivideByZeroException`：当 `a2` 为零时会出现这种情况。
- `OverflowException`：如果 `a1` 和 `a2` 相除的结果小于 `decimal` 的最小可能值或大于 `decimal` 的最大可能值。

下面的程序说明了 `Decimal.Divide(Decimal, Decimal)` 方法的使用：

### 例 1

```csharp
// C# program to demonstrate the
// Decimal.Divide(Decimal,
// Decimal) Method
using System;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// Declaring the decimal variables
            Decimal a1 = 4.02m;
            Decimal a2 = 2.01m;

// dividing the two Decimal value
            // using Divide() method;
            Decimal value = Decimal.Divide(a1, a2);

// Display the division
            Console.WriteLine("Result of "+
                 "division : {0}", value);
        }

catch (OverflowException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```csharp
Result of division : 2
```

### 示例 2：`OverflowException` 程序

```csharp
// C# program to demonstrate the
// Decimal.Divide(Decimal, 
// Decimal) Method
using System;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// Declaring the decimal variables
            Decimal a1 = Decimal.MaxValue;
            Decimal a2 = 0.01m;

// dividing the two Decimal value
            // using Divide() method;
            Decimal value = Decimal.Divide(a1, a2);

// Display the division
            Console.WriteLine("Result of "+
                 "division : {0}", value);
        }

catch (OverflowException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```csharp
Exception Thrown: System.OverflowException
```

### 例 3：`DivideByZeroException` 程序

```csharp
// C# program to demonstrate the
// Decimal.Divide(Decimal,
// Decimal) Method
using System;

class GFG {

// Main Method
    public static void Main()
    {
        try {

// Declaring the decimal variables
            Decimal a1 = 4.02m;
            Decimal a2 = 0.00m;

// dividing the two Decimal value
            // using Divide() method;
            Decimal value = Decimal.Divide(a1, a2);

// Display the division
            Console.WriteLine("Result of"+
                " division : {0}", value);
        }

catch (DivideByZeroException e)
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```csharp
Exception Thrown: System.DivideByZeroException
```

## 参考

- [https://docs.microsoft.com/en-us/dotnet/api/system.decimal.divide?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.decimal.divide?view=netframework-4.7.2)