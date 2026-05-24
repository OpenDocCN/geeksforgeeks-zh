# C# 中 Int16、Int32、Int64 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-int16-int32-and-int64-in-c-sharp/](https://www.geeksforgeeks.org/difference-between-int16-int32-and-int64-in-c-sharp/)

`Int16`：此结构用于表示 16 位有符号整数。`Int16` 可以存储在 **-32768 到 +32767** 范围内的包括负值和正值的两种类型的值。

## 示例代码

```cs
// C# program to show the
// Int16 Struct usage

using System;
using System.Text;

public
class GFG {

// Main Method
  static void Main(string[] args) {

// printing minimum & maximum values
    Console.WriteLine("Minimum value of Int16: " 
                      + Int16.MinValue);
    Console.WriteLine("Maximum value of Int16: " 
                      + Int16.MaxValue);
    Console.WriteLine();

// Int16 array
    Int16[] arr1 = {-3, 0, 1, 3, 7};

foreach (Int16 i in arr1)
    { 
      Console.WriteLine(i);
    }
  }
}
```

## 输出

```cs
Minimum value of Int16: -32768
Maximum value of Int16: 32767
```

`Int32`：这个结构用来表示 32 位有符号整数。`Int32` 可以存储在 **-2147483648 到 +2147483647** 范围内的包括负值和正值的两种类型的值。

## 示例代码

```cs
// C# program to show the
// Int32 struct usage

using System;
using System.Text;

public
class GFG {

// Main Method
  static void Main(string[] args) {

// printing minimum & maximum values
    Console.WriteLine("Minimum value of Int32: " 
                      + Int32.MinValue);
    Console.WriteLine("Maximum value of Int32: " 
                      + Int32.MaxValue);
    Console.WriteLine();

// Int32 array
    Int32[] arr1 = {-3, 0, 1, 3, 7};

foreach (Int32 i in arr1)
    { 
      Console.WriteLine(i);
    }
  }
}
```

## 输出

```cs
Minimum value of Int32: -2147483648
Maximum value of Int32: 2147483647
```

`Int64`：这个结构用来表示 64 位有符号整数。`Int64` 可以存储介于 **-9,223,372,036,854,775,808 至 +9,223,372,036,854,775,807** 范围之间的包括负值和正值的两种类型的值。

## 示例代码

```cs
// C# program to show 
// Int64 struct usage
using System;
using System.Text;

public class GFG {

// Main Method
  static void Main(string[] args) {

// printing minimum & maximum values
    Console.WriteLine("Minimum value of Int64: " 
                      + Int64.MinValue);
    Console.WriteLine("Maximum value of Int64: " 
                      + Int64.MaxValue);
    Console.WriteLine();

// Int64 array
    Int64[] arr1 = {-3, 0, 1, 3, 7};

foreach (Int64 i in arr1)
    { 
      Console.WriteLine(i);
    }
  }
}
```

## 输出

```cs
Minimum value of Int64: -9223372036854775808
Maximum value of Int64: 9223372036854775807
```

## C# 中 Int16、Int32、Int64 的区别

| 序号 | `Int16` | `Int32` | `Int64` |
| :--- | :--- | :--- | :--- |
| **1.** | `Int16` 用于表示 16 位有符号整数。 | `Int32` 用于表示 32 位有符号整数。 | `Int64` 用于表示 64 位有符号整数。 |
| **2.** | `Int16` 代表有符号整数。 | `Int32` 也代表有符号整数。 | `Int64` 也代表有符号整数。 |
| **3.** | 可以存储正整数和负整数。 | 也可以存储正整数和负整数。 | 也可以存储正整数和负整数。 |
| **4.** | 在内存中需要 2 字节空间。 | 占用内存中 4 字节空间。 | 占用内存中 8 字节空间。 |
| **5.** | `Int16` 的范围是从 -32768 到 +32767。 | `Int32` 的范围是从 -2147483648 到 +2147483647。 | `Int64` 的范围是从 -9223372036854775808 到 +9223372036854775807。 |
| **6.** | 声明 `Int16` 的语法：<br>`Int16 variable_name;` | 声明 `Int32` 的语法：<br>`Int32 variable_name;` | 声明 `Int64` 的语法：<br>`Int64 variable_name;` |