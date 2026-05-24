# c# 中 UInt16、UInt32 和 UInt64 的区别

> 原文:[https://www . geeksforgeeks . org/uint 16-uint 32-和-uint64-in-c-sharp/](https://www.geeksforgeeks.org/difference-between-uint16-uint32-and-uint64-in-c-sharp/) 之间的差异

[**UInt16**](https://www.geeksforgeeks.org/c-sharp-uint16-struct/) **:** 此结构用于表示 16 位无符号整数。**U****int 16**只能存储范围从 **0** **到 65535** 的正值。

**例:**

## C#

```cs
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

**输出:**

```cs
Minimum value of UInt16: 0
Maximum value of UInt16: 65535

13
0
1
3
7

```

[**UInt32**](https://www.geeksforgeeks.org/c-sharp-uint32-struct/?ref=rp) **:** 此结构用于表示 32 位无符号整数。 **UInt32** 只能存储范围从 **0 到 4294967295** 的正值。

**例:**

## C#

```cs
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

**输出:**

```cs
Minimum value of UInt32: 0
Maximum value of UInt32: 4294967295

13
0
1
3
7

```

[**UInt64**](https://www.geeksforgeeks.org/c-sharp-uint64-struct/?ref=rp) **:** 此结构用于表示 64 位无符号整数。 **UInt64** 只能存储从 **0 到** **18，446，744，073，709，551，615 的正值。**

**例:**

## C#

```cs
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

**输出:**

```cs
Minimum value of UInt64: 0
Maximum value of UInt64: 18446744073709551615

13
0
1
3
7

```

**c# 中 UInt16、UInt32 和 UInt64 的区别**

<figure class="table">

| **先生否** | uint 16 | **UINT32**

 | **UINT64** |
| **1。** | UInt16 用于表示 16 位无符号整数 | UInt32 用于表示 32 位无符号整数。 | UInt64 用于表示 64 位无符号整数。 |
| **2。** | UInt16 代表无符号整数。 | UInt32 也代表无符号整数。 | UInt64 也代表无符号整数。 |
| **3。** | 只能存储正整数。 | 也只能存储正整数。 | 也只能存储正整数。 |
| **4。** | 在内存中需要 2 字节 空间。 | 占用内存中 4-字节 空间。 | 占用内存中 8-字节 空间。 |
| **5。** | UInt16 的范围从 0 到 65535。 | UInt32 范围从 0 到 4294967295。 | UInt64 范围从 0 到 18446744073709551615。 |
| **6。** | 声明 UInt16 的语法:

```cs
UInt16 variable_name;

```

 | 声明 UInt32 的语法:

```cs
UInt32 variable_name;

```

 | 声明 UInt64 的语法:

```cs
UInt64 variable_name;

```

 |

</figure>