# C# | Byte。相等(对象)方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-byte-equalsobject-method/](https://www.geeksforgeeks.org/c-sharp-byte-equalsobject-method/)

此方法用于获取一个值，该值指示当前实例是否等于指定的对象。

> **语法:**公共覆盖 bool Equals(对象 obj)；
> 这里，需要一个对象与当前实例进行比较，否则为空。
> 
> **返回值:**如果 obj 是 Byte 的实例，并且等于当前实例的值，则该方法返回 *true* ，否则返回 false。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to demonstrate the
// Byte.Equals(Object) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        byte value1 = 10;

        // Declaring and initializing value2
        object value2 = 2/47;

        // using Equals(object) method
        bool status = value1.Equals(value2);

        // checking the status
        if (status)
            Console.WriteLine("{0} is equal to {1}",
                                    value1, value2);
        else
            Console.WriteLine("{0} is not equal to {1}",
                                        value1, value2);
    }
}
```

**Output:**

```cs
10 is not equal to 0

```

**例 2:**

```cs
// C# program to demonstrate the
// Byte.Equals(Object) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        get(5, 5);
        get(5, 4);
        get(10, 20);

        // using explicit type casting
        get(7, (byte)7);
    }

    // defining get() method
    public static void get(byte value1,
                        object value2)
    {

        // using Equals(object) method
        bool status = value1.Equals(value2);

        // checking the status
        if (status)
            Console.WriteLine("{0} is equal to {1}",
                                    value1, value2);
        else
            Console.WriteLine("{0} is not equal to {1}",
                                        value1, value2);
    }
}
```

**Output:**

```cs
5 is not equal to 5
5 is not equal to 4
10 is not equal to 20
7 is equal to 7

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . byte . equals？view = net framework-4 . 7 . 2 # System _ Byte _ Equals _ System _ Object _](https://docs.microsoft.com/en-us/dotnet/api/system.byte.equals?view=netframework-4.7.2# System_Byte_Equals_System_Object_)