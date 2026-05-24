# C# 中 Int16 和 UInt16 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-int16-and-uint16-in-c-sharp/](https://www.geeksforgeeks.org/difference-between-int16-and-uint16-in-c-sharp/)

`Int16`：此结构用于表示 16 位有符号整数。`Int16` 可以存储在 **-32768 到 +32767** 范围内的包括负值和正值的两种类型的值。

**例：**

### C#

```cs
// C# program to show the
// difference between Int16
// and UInt16

using System;
using System.Text;

public class GFG {

    // Main Method
    static void Main(string[] args) {

        // printing minimum & maximum values
        Console.WriteLine("Minimum value of Int16: " + Int16.MinValue);
        Console.WriteLine("Maximum value of Int16: " + Int16.MaxValue);
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

**输出：**

```cs
Minimum value of Int16: -32768
Maximum value of Int16: 32767
```

`UInt16`：此结构用于表示 16 位无符号整数。`UInt16` 只能存储范围从 **0 到 65535** 的正值。

**例：**

### C#

```cs
// C# program to show the
// difference between Int16
// and UInt16

using System;
using System.Text;

public class GFG {

    // Main Method
    static void Main(string[] args) {

        // printing minimum & maximum values
        Console.WriteLine("Minimum value of UInt16: " + UInt16.MinValue);
        Console.WriteLine("Maximum value of UInt16: " + UInt16.MaxValue);
        Console.WriteLine();

        // UInt16 array
        UInt16[] arr1 = { 13, 0, 1, 3, 7};

        foreach (UInt16 i in arr1)
        {
            Console.WriteLine(i);
        }
    }
}
```

**输出：**

```cs
Minimum value of UInt16: 0
Maximum value of UInt16: 65535
```

## Int16 和 UInt16 在 C# 中的区别

| **序号** | **Int16** | **UInt16** |
| :--- | :--- | :--- |
| **1.** | `Int16` 用于表示 16 位有符号整数。 | `UInt16` 用于表示 16 位无符号整数。 |
| **2.** | `Int16` 代表有符号整数。 | `UInt16` 代表无符号整数。 |
| **3.** | 可以存储正整数和负整数。 | 只能存储正整数。 |
| **4.** | 在内存中需要 2 字节空间。 | 它还占用内存中的 2 字节空间。 |
| **5.** | `Int16` 的范围是从 -32768 到 +32767。 | `UInt16` 的范围从 0 到 65535。 |
| **6.** | 声明 `Int16` 的语法：<br>`Int16 variable_name;` | 声明 `UInt16` 的语法：<br>`UInt16 variable_name;` |