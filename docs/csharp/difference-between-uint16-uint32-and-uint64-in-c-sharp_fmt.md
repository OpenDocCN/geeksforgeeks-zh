# C# 中 UInt16、UInt32 和 UInt64 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-uint16-uint32-and-uint64-in-c-sharp/](https://www.geeksforgeeks.org/difference-between-uint16-uint32-and-uint64-in-c-sharp/)

`UInt16`：此结构用于表示 16 位无符号整数。`UInt16` 只能存储范围从 `0` 到 `65535` 的正值。

**例：**

## C\#

```csharp
// C# program to show the
// UInt16 struct
using System;
using System.Text;

public class GFG{

    // Main Method
    static void Main(string[] args)
    {

        //printing minimum & maximum values
        Console.WriteLine("Minimum value of UInt16: "
                          + UInt16.MinValue);
        Console.WriteLine("Maximum value of UInt16: "
                          + UInt16.MaxValue);
        Console.WriteLine();

        // Int16 array
        UInt16[] arr1 = { 13, 0, 1, 3, 7};

        foreach (UInt16 i in arr1)
        {
            Console.WriteLine(i);
        }
    }
}
```

**输出：**

```csharp
Minimum value of UInt16: 0
Maximum value of UInt16: 65535
```

`UInt32`：此结构用于表示 32 位无符号整数。`UInt32` 只能存储范围从 `0` 到 `4294967295` 的正值。

**例：**

## C\#

```csharp
// C# program to show the
// UInt32 struct
using System;
using System.Text;

public class GFG{

    // Main Method
    static void Main(string[] args)
    {

        // printing minimum & maximum values
        Console.WriteLine("Minimum value of UInt32: "
                          + UInt32.MinValue);
        Console.WriteLine("Maximum value of UInt32: "
                          + UInt32.MaxValue);
        Console.WriteLine();

        // Int32 array
        UInt32[] arr1 = { 13, 0, 1, 3, 7};

        foreach (UInt32 i in arr1)
        {
            Console.WriteLine(i);
        }
    }
}
```

**输出：**

```csharp
Minimum value of UInt32: 0
Maximum value of UInt32: 4294967295
```

`UInt64`：此结构用于表示 64 位无符号整数。`UInt64` 只能存储从 `0` 到 `18446744073709551615` 的正值。

**例：**

## C\#

```csharp
// C# program to show the
// UInt64 struct
using System;
using System.Text;

public class GFG{

    // Main Method
    static void Main(string[] args)
    {

        // printing minimum & maximum values
        Console.WriteLine("Minimum value of UInt64: "
                          + UInt64.MinValue);
        Console.WriteLine("Maximum value of UInt64: "
                          + UInt64.MaxValue);
        Console.WriteLine();

        // Int64 array
        UInt64[] arr1 = { 13, 0, 1, 3, 7};

        foreach (UInt64 i in arr1)
        {
            Console.WriteLine(i);
        }
    }
}
```

**输出：**

```csharp
Minimum value of UInt64: 0
Maximum value of UInt64: 18446744073709551615
```

## C# 中 UInt16、UInt32 和 UInt64 的区别

| 特性 | `UInt16` | `UInt32` | `UInt64` |
| :--- | :--- | :--- | :--- |
| **1. 用途** | 用于表示 16 位无符号整数。 | 用于表示 32 位无符号整数。 | 用于表示 64 位无符号整数。 |
| **2. 类型** | 代表无符号整数。 | 代表无符号整数。 | 代表无符号整数。 |
| **3. 取值** | 只能存储正整数。 | 只能存储正整数。 | 只能存储正整数。 |
| **4. 内存占用** | 在内存中需要 2 字节空间。 | 占用内存中 4 字节空间。 | 占用内存中 8 字节空间。 |
| **5. 范围** | 范围从 `0` 到 `65535`。 | 范围从 `0` 到 `4294967295`。 | 范围从 `0` 到 `18446744073709551615`。 |
| **6. 声明语法** | `UInt16 variable_name;` | `UInt32 variable_name;` | `UInt64 variable_name;` |