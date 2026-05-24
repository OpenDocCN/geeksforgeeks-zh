# C# | Byte.CompareTo(byte)方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-byte-comparetobyte-method/](https://www.geeksforgeeks.org/c-sharp-byte-comparetobyte-method/)

此方法用于将此实例与指定的 8 位无符号整数进行比较，并返回其相对值的指示。

**语法：**

```cs
public int CompareTo (byte value);
```

这里，`value` 是一个 8 位无符号整数进行比较。

**返回值：** 该方法返回一个有符号整数，表示该实例与 `value` 的相对顺序。

*   **小于零：** 此实例小于 `value`。
*   **零：** 此实例等于 `value`。
*   **大于零：** 此实例大于 `value`。

以下程序说明了 `Byte.CompareTo(byte)` 方法的使用：

## 示例 1

```cs
// C# program to demonstrate
// Byte.CompareTo(byte)
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring val1 and val2
        byte val1, val2;

        // initializing the val1,
        // val2 and val3
        val1 = 12;
        val2 = 13;

        // getting compared constant
        // using CompareTo method
        int i = val2.CompareTo(val1);

        // checking the condition
        if (i > 0)
            Console.Write("val2 is greater than val1");

        else if (i < 0)
            Console.Write("val2 is less than val1");

        else
            Console.Write("val1 is equal to val1");
    }
}
```

**输出：**

```cs
val2 is greater than val1
```

## 示例 2

```cs
// C# program to demonstrate
// Byte.CompareTo(byte)
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // checking the condition
        // calling check() method
        check((byte)10, (byte)20);
        check((byte)30, (byte)20);
        check((byte)10, (byte)10);
        check((byte)5, (byte)7);
        check((byte)40, (byte)50);
        check((byte)1, (byte)2);
    }

    // Defining the check method
    public static void check(byte v1, byte v2)
    {
        // getting compared constant
        // using CompareTo() method
        int i = v1.CompareTo(v2);

        // checking the condition
        if (i > 0)
            Console.WriteLine(v1 + " is greater than " + v2);

        else if (i < 0)
            Console.WriteLine(v1 + " is less than " + v2);

        else
            Console.WriteLine(v1 + " is equal to " + v2);
    }
}
```

**输出：**

```cs
10 is less than 20
30 is greater than 20
10 is equal to 10
5 is less than 7
40 is less than 50
1 is less than 2
```

**参考：**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.byte.compareto?view=netframework-4.7.2#System_Byte_CompareTo_System_Byte_](https://docs.microsoft.com/en-us/dotnet/api/system.byte.compareto?view=netframework-4.7.2#System_Byte_CompareTo_System_Byte_)