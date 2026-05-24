# C# | BitConverter。ToBoolean()方法

> 原文:[https://www . geesforgeks . org/c-sharp-bit converter-to boolean-method/](https://www.geeksforgeeks.org/c-sharp-bitconverter-toboolean-method/)

此方法用于返回从字节数组中指定位置的字节转换而来的布尔值。

**语法:**

```cs
public static bool ToBoolean (byte[] value, int startIndex);
```

**参数:**

> **值:**是需要的字节数组。
> **startIndex:** 是值内字节的索引。

**返回值:**如果值中 startIndex 处的字节非零，则该方法返回真，否则返回假。

**异常:**

*   **ArgumentNullException:** 如果值为空。
*   **argumentoutofrangerexception:**如果 startIndex 小于零或大于值的长度减 1。

以下程序说明了**位转换器的使用。ToBoolean(Byte[]，Int32)方法**:

**例 1:**

```cs
// C# program to demonstrate
// BitConverter.ToBoolean(bytes, index));
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Define an array of byte values.
            byte[] bytes = { 0, 1, 2, 4, 8, 16, 32, 64 };

            // Display the values of the myArr.
            Console.Write("Initial Array: ");

            // calling the PrintIndexAndValues()
            // method to print
            PrintIndexAndValues(bytes);

            for (int index = 0; index < bytes.Length; index++) {

                bool values = BitConverter.ToBoolean(bytes, index);
                Console.WriteLine("index     element           bool");
                Console.WriteLine(" {0}         {1}                   {2}",
                                         index, bytes[index], values);
            }
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArgumentOutOfRangeException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining the method
    // PrintIndexAndValues
    public static void PrintIndexAndValues(byte[] myArr)
    {
        for (int i = 0; i < myArr.Length; i++) {

            Console.Write("{0} ", myArr[i]);
        }
        Console.WriteLine();
        Console.WriteLine();
    }
}
```

**Output:**

```cs
Initial Array: 0 1 2 4 8 16 32 64 

index     element           bool
 0         0                   False
index     element           bool
 1         1                   True
index     element           bool
 2         2                   True
index     element           bool
 3         4                   True
index     element           bool
 4         8                   True
index     element           bool
 5         16                   True
index     element           bool
 6         32                   True
index     element           bool
 7         64                   True

```

**例 2:** 为*argumentout of range exception*

```cs
// C# program to demonstrate
// BitConverter.ToBoolean(bytes, index));
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Define an array of byte values.
            byte[] bytes = { 0, 1, 2, 4, 8, 16, 32, 64 };

            // Display the values of the myArr.
            Console.Write("Initial Array: ");

            // calling the PrintIndexAndValues()
            // method to print
            PrintIndexAndValues(bytes);

            Console.WriteLine("startindex in less than zero");
            bool values = BitConverter.ToBoolean(bytes, -1);
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArgumentOutOfRangeException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining the method
    // PrintIndexAndValues
    public static void PrintIndexAndValues(byte[] myArr)
    {
        for (int i = 0; i < myArr.Length; i++) {

            Console.Write("{0} ", myArr[i]);
        }
        Console.WriteLine();
        Console.WriteLine();
    }
}
```

**输出:**

```cs
Initial Array: 0 1 2 4 8 16 32 64 

startindex in less than zero
Exception Thrown: System.ArgumentOutOfRangeException

```

**示例 3:** 适用于*参数异常*

```cs
// C# program to demonstrate
// BitConverter.ToBoolean(bytes, index));
// Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // Define an array of byte values.
            byte[] bytes = null;

            // Getting bool value
            Console.WriteLine("byte array is null");
            bool values = BitConverter.ToBoolean(bytes, 0);
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (ArgumentOutOfRangeException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出:**

```cs
byte array is null
Exception Thrown: System.ArgumentNullException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . bit converter . to boolean？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.bitconverter.toboolean?view=netframework-4.7.2)