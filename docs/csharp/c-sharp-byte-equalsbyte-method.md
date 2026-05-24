# C# | Byte。相等(字节)法

> 原文:[https://www . geesforgeks . org/c-sharp-byte-equals byte-method/](https://www.geeksforgeeks.org/c-sharp-byte-equalsbyte-method/)

此方法用于返回一个值，该值指示此实例和指定的字节对象是否表示相同的值。
**语法:**

```cs
public bool Equals (byte obj);
```

这里， *obj* 是一个字节对象，用来与这个实例进行比较。
**返回值:**此方法返回*真*如果 *obj* 等于此实例，否则返回*假*。
以下程序说明了**字节的使用。等于(字节)**方法:
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Byte.Equals(byte) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        // Declaring val1 and val2
        byte val1, val2;

        // initializing the val1, val2 and val3
        val1 = 12;
        val2 = 13;

        // getting compared constant
        // using CompareTo method
        bool i = val2.Equals(val1);

        // checking the condition
        if (i)
            Console.Write("val2 is equal to val1");

        else
            Console.Write("val2 is not equal to val1");
    }
}
```

**Output:** 

```cs
val2 is not equal to val1
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate
// Byte.Equals(byte) Method
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
        check((byte)1, (byte)1);
    }

    // Defining the check method
    public static void check(byte v1, byte v2)
    {

        // getting compared constant
        // using Equals() method
        bool i = v1.Equals(v2);

        // checking the condition
        if (i)
            Console.WriteLine(v1 + " is equal to " + v2);

        else
            Console.WriteLine(v1 + " is not equal to " + v2);
    }
}
```

**Output:** 

```cs
10 is not equal to 20
30 is not equal to 20
10 is equal to 10
5 is not equal to 7
40 is not equal to 50
1 is equal to 1
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . byte . equals？view = net framework-4 . 7 . 2 # System _ Byte _ Equals _ System _ Byte _](https://docs.microsoft.com/en-us/dotnet/api/system.byte.equals?view=netframework-4.7.2# System_Byte_Equals_System_Byte_)