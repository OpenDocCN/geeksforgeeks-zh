# c# 中 Int64 和 UInt64 的区别

> 原文:[https://www . geeksforgeeks . org/in-int 64-和-uint64-in-c-sharp/](https://www.geeksforgeeks.org/difference-between-int64-and-uint64-in-c-sharp/) 之间的差异

[**Int64**](https://www.geeksforgeeks.org/c-sharp-int-64-struct/?ref=rp) **:** 这个结构用来表示 64 位有符号整数。 **Int64** 可以存储介于 **-9，223，372，036，854，775，808 至+9，223，372，036，854，775，807** 范围之间的包括负值和正值的两种类型的值

**例:**

## C#

```cs
// C# program to show the
// difference between Int64
// and UInt64

using System;
using System.Text;

public
class GFG {

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

**输出:**

```cs
Minimum value of Int64: -9223372036854775808
Maximum value of Int64: 9223372036854775807

-3
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
// difference between Int64 
// and UInt64

using System;
using System.Text;

public class GFG{

    // Main Method
    static void Main(string[] args)
    {

        //printing minimum & maximum values
        Console.WriteLine("Minimum value of UInt64: "
                          + UInt64.MinValue);
        Console.WriteLine("Maximum value of UInt64: "
                          + UInt64.MaxValue);
        Console.WriteLine();

        //Int64 array
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

**c# 中 Int64 和 UInt64 的区别**

<figure class="table">

| **先生否** | **INT64** | **UINT64** |
| **1。** | Int64 用于表示 64 位有符号整数。 | UInt64 用于表示 64 位无符号整数。 |
| **2。** | Int64 代表有符号整数。 | UInt64 代表无符号整数。 |
| **3。** | 可以存储正整数和负整数。 | 只能存储正整数。 |
| **4。** | 占用内存中 8-字节 空间。 | 还需要占用内存中 8-字节 的空间。 |
| **5。** | Int64 的范围是从 -9223372036854775808 到+922372036854775807。 | UInt64 范围从 0 到 18446744073709551615。 |
| **6。** | 声明 Int64 的语法:

```cs
Int64 variable_name;

```

 | 声明 UInt64 的语法:

```cs
UInt64 variable_name;

```

 |

</figure>