# c# 中 Int32 和 UInt32 的区别

> 原文:[https://www . geeksforgeeks . org/in-int 32 和-uint32-in-c-sharp 之间的差异/](https://www.geeksforgeeks.org/difference-between-int32-and-uint32-in-c-sharp/)

[**Int32**](https://www.geeksforgeeks.org/c-sharp-int32-struct/?ref=rp) **:** 这个结构用来表示 32 位有符号整数。 **Int32** 可以存储在 **-2147483648 到+2147483647** 范围内的包括负值和正值的两种类型的值。

**例:**

## C#

```cs
// C# program to show the
// difference between Int32
// and UInt32

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

**输出:**

```cs
Minimum value of Int32: -2147483648
Maximum value of Int32: 2147483647

-3
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
// difference between Int32 
// and UInt32

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

**c# 中 Int32 和 UInt32 的区别**

<figure class="table">

| **先生否** | **INT32** | **UINT32** |
| **1。** | Int32 用于表示 32 位有符号整数。 | UInt32 用于表示 32 位无符号整数。 |
| **2。** | Int32 代表有符号整数。 | UInt32 代表无符号整数。 |
| **3。** | 可以存储正整数和负整数。 | 只能存储正整数。 |
| **4。** | 占用内存中 4-字节 空间。 | 还需要占用内存中 4-字节 的空间。 |
| **5。** | Int32 的范围是从 -2147483648 到+2147483647。 | UInt32 范围从 0 到 4294967295。 |
| **6。** | 声明 Int32 的语法:

```cs
Int32 variable_name;

```

 | 声明 UInt32 的语法:

```cs
UInt32 variable_name;

```

 |

</figure>