# C# | Byte。比较(对象)方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-byte-compare object-method/](https://www.geeksforgeeks.org/c-sharp-byte-comparetoobject-method/)

此方法用于将当前实例与指定对象进行比较，并返回其相对值的符号。无论值如何，字节的任何实例都将被视为大于空。

**语法:**

```cs
public int CompareTo (object value);
```

这里，它需要一个对象进行比较，或者为 null。

**返回值:**返回一个有符号整数，表示当前实例和*值*参数的相对顺序，如下所示:

*   **小于零:**如果当前实例<值
*   **如果当前实例=值，则为零:**
*   如果当前实例>值**或**值为空，则**大于零:**。

**异常:**如果值不是字节，则抛出*参数异常*。

以下程序说明了*字节的使用。比较(对象)*方法

**例 1:**

```cs
// C# program to demonstrate the
// Byte.CompareTo(object) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring and initializing value1
            byte value1 = 10;

            // Declaring and initializing value2
            // converting to byte using explicit
            // type casting
            object value2 = (byte)87;

            // using CompareTo() method
            int status = value1.CompareTo(value2);

            // checking the status
            if (status > 0)
                Console.WriteLine("{0} is greater than {1}",
                                            value1, value2);

            else if (status < 0)
                Console.WriteLine("{0} is less than {1}",
                                         value1, value2);
            else
                Console.WriteLine("{0} is equal to {1}",
                                        value1, value2);
        }

        catch (ArgumentException e) 
        {
            Console.WriteLine("value2 must be Byte");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
10 is less than 87

```

**示例 2:** 适用于*参数异常*

```cs
// C# program to demonstrate the
// Byte.CompareTo(object) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring and initializing value1
            byte value1 = 10;

            // Declaring and initializing value2
            object value2 = (long)569874514;

            // using CompareTo() method
            int status = value1.CompareTo(value2);

            // checking the status
            if (status > 0)
                Console.WriteLine("{0} is greater than {1}",
                                            value1, value2);

            else if (status < 0)
                Console.WriteLine("{0} is less than {1}",
                                         value1, value2);
            else
                Console.WriteLine("{0} is equal to {1}",
                                        value1, value2);
        }

        catch (ArgumentException e) 
        {
            Console.WriteLine("value2 must be Byte");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
value2 must be Byte
Exception Thrown: System.ArgumentException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . byte . compare to？view = net framework-4 . 7 . 2 # System _ Byte _ compare to _ System _ Object _](https://docs.microsoft.com/en-us/dotnet/api/system.byte.compareto?view=netframework-4.7.2# System_Byte_CompareTo_System_Object_)