# C# | Convert。FromBase64String(字符串)方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-convert-from base64 string-method/](https://www.geeksforgeeks.org/c-sharp-convert-frombase64stringstring-method/)

此方法用于将指定的字符串转换为等效的 8 位无符号整数数组，该字符串将二进制数据编码为 64 位基数。

**语法:**

```cs
public static byte[] FromBase64String (string s);
```

这里， *s* 是要转换的字符串。

**返回值:**这个方法返回一个 8 位无符号整数数组，相当于*的*。

**异常**

*   **参数空异常**:如果 *s* 为空。
*   **格式异常**:如果 *s* 的长度，忽略空格字符，不是零或者 4 的倍数。*或**s*的格式无效。 **s** 包含一个非 base-64 字符、两个以上的填充字符或填充字符中的一个非空白字符。

以下程序说明了**转换的使用。FromBase64String(字符串)**方法:

**例 1:**

```cs
// C# program to demonstrate the
// Convert.FromBase64String(String) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // defining and initializing
            // byte1 and byte2
            byte[] byte1 = {2, 4, 6, 8, 10, 
                       12, 14, 16, 18, 20};

            byte[] byte2 = {10, 20, 30, 
                                40, 50};

            // calling get() Method
            get(byte1, "byte1");

            Console.WriteLine("");
            get(byte2, "byte2");
        }

        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        catch (FormatException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), 
                                  e.Message);
        }
    }

    // Defining get() method
    public static void get(byte[] bytes, string str)
    {

        Console.WriteLine("For {0}", str);

        // converting byte to base 64 string
        string s = Convert.ToBase64String(bytes);

        Console.WriteLine("The base 64 string: '{0}'", s);
        Console.WriteLine("The base 64 string: '{0}'", s);

        // converting base 64 string to byte array
        byte[] val = Convert.FromBase64String(s);
        Console.WriteLine("Converted byte value: {0}", 
                          BitConverter.ToString(val));
    }
}
```

**Output:**

```cs
For byte1
The base 64 string: 'AgQGCAoMDhASFA=='
The base 64 string: 'AgQGCAoMDhASFA=='
Converted byte value: 02-04-06-08-0A-0C-0E-10-12-14

For byte2
The base 64 string: 'ChQeKDI='
The base 64 string: 'ChQeKDI='
Converted byte value: 0A-14-1E-28-32

```

**示例 2:** 适用于*参数异常*

```cs
// C# program to demonstrate the
// Convert.FromBase64String(String) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // defining and initializing
            // byte1 and byte2
            byte[] byte1 = {2, 4, 6, 8, 10, 12,
                               14, 16, 18, 20};

            // calling get() Method
            get(byte1, "byte1");
            Console.WriteLine("");

            // converting base 64 string to byte array
            Console.WriteLine("s is null");

            byte[] val = Convert.FromBase64String(null);
            Console.WriteLine("Converted byte value: {0}",
                              BitConverter.ToString(val));
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (FormatException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining get() method
    public static void get(byte[] bytes, string str)
    {

        Console.WriteLine("For {0}", str);

        // converting byte to base 64 string
        string s = Convert.ToBase64String(bytes);
        Console.WriteLine("The base 64 string: '{0}'", s);

        // converting base 64 string to byte array
        byte[] val = Convert.FromBase64String(s);
        Console.WriteLine("Converted byte value: {0}", 
                          BitConverter.ToString(val));
    }
}
```

**Output:**

```cs
For byte1
The base 64 string: 'AgQGCAoMDhASFA=='
Converted byte value: 02-04-06-08-0A-0C-0E-10-12-14

s is null
Exception Thrown: System.ArgumentNullException

```

**例 3:** 为*格式异常*

```cs
// C# program to demonstrate the
// Convert.FromBase64String(String) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {

        try {

            // defining and initializing 
            // byte1 and byte2
            byte[] byte1 = {2, 4, 6, 8, 10, 
                       12, 14, 16, 18, 20};

            // calling get() Method
            get(byte1, "byte1");
            Console.WriteLine("");

            // converting base 64 
            // string to byte array
            Console.WriteLine("s contains a non-base-64 character");

            byte[] val = Convert.FromBase64String("sun");
            Console.WriteLine("Converted byte value: {0}", 
                              BitConverter.ToString(val));
        }
        catch (ArgumentNullException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
        catch (FormatException e) {

            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining get() method
    public static void get(byte[] bytes, string str)
    {

        Console.WriteLine("For {0}", str);

        // converting byte to base 64 string
        string s = Convert.ToBase64String(bytes);
        Console.WriteLine("The base 64 string: '{0}'", s);

        // converting base 64 string to byte array
        byte[] val = Convert.FromBase64String(s);
        Console.WriteLine("Converted byte value: {0}",
                           BitConverter.ToString(val));
    }
}
```

**Output:**

```cs
For byte1
The base 64 string: 'AgQGCAoMDhASFA=='
Converted byte value: 02-04-06-08-0A-0C-0E-10-12-14

s contains a non-base-64 character
Exception Thrown: System.FormatException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . convert . from base64 string？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.convert.frombase64string?view=netframework-4.7.2)