# C# | Convert。ToBase64String()方法| Set-1

> 原文:[https://www . geesforgeks . org/c-sharp-convert-to base64 string-method-set-1/](https://www.geeksforgeeks.org/c-sharp-convert-tobase64string-method-set-1/)

**转换。ToBase64String()方法**用于将 8 位无符号整数数组的值转换为其等效的字符串表示形式，该字符串表示形式以 64 位为基数进行编码。此方法的重载中有以下 4 种方法:

*   **ToBase64String(Byte[]，Int32，Int32)方法**
*   **ToBase64String(Byte[]，Int32，Int32，Base64FormattingOptions)方法**
*   **ToBase64String(Byte[]，Base64FormattingOptions)方法**
*   **ToBase64String(Byte[])方法**

**这里我们只讨论**第一种**方法。**

****ToBase64String(Byte[]，Int32，Int32)方法**用于将 8 位无符号整数数组的子集转换为其等效的字符串表示形式，该字符串表示形式用基数为 64 的数字进行编码。参数将子集指定为输入数组中的偏移量，以及要转换的数组中的元素数量。**

****语法:****

```cs
public static string ToBase64String (byte[] inArray, int offset, int length);
```

****参数:****

*   ****inArray** :是一个 8 位无符号整数的数组。**
*   ****偏移**:是*在*的偏移。**
*   ****长度**:是要转换的 *inArray* 的元素个数。**

****返回值:**该方法从位置偏移开始，返回 *inArray* 长度元素以 64 为基数的字符串表示。**

****异常:****

*   ****ArgumentNullException:** 如果 *inArray* 为空。**
*   ****argumentout of range exception:**如果*偏移量*或*长度*为负**或**或*偏移量*加上*长度*大于*或*的长度。**

**以下程序说明了**转换的使用。ToBase64String(Byte[]，Int32，Int32)** 方法:**

****例 1:****

```cs
// C# program to demonstrate the
// Convert.ToBase64String() Method
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

        byte[] byte2 = {10, 20, 30, 40, 50};

        // calling get() Method
        get(byte1, "byte1");

        Console.WriteLine("");
        get(byte2, "byte2");
    }

    catch (ArgumentNullException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }

    catch (ArgumentOutOfRangeException e) {

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
    string val = Convert.ToBase64String(bytes,
                             0, bytes.Length);

    // display the converted string
    Console.WriteLine("converted string: {0}", val);
}
}
```

****Output:**

```cs
For byte1
converted string: AgQGCAoMDhASFA==

For byte2
converted string: ChQeKDI=

```** 

****示例 2:** 适用于*参数异常***

```cs
// C# program to demonstrate the
// Convert.ToBase64String() Method
using System;

class GFG {

// Main Method
public static void Main()
{
    try {

        // defining and initializing
        // byte1
        byte[] byte1 = {2, 4, 6, 8, 10,
                   12, 14, 16, 18, 20};

        // calling get() Method
        get(byte1, "byte1");

        Console.WriteLine("");

        // converting base 64 string 
        // to byte array
        Console.WriteLine("bye array is null");

        string val = Convert.ToBase64String(null, 0, 10);
        Console.WriteLine("Converted byte value: {0}", val);
    }

    catch (ArgumentNullException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }

    catch (ArgumentOutOfRangeException e) {

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
    string val = Convert.ToBase64String(bytes, 
                             0, bytes.Length);

    // display the converted string
    Console.WriteLine("converted string: {0}", val);
}
}
```

****Output:**

```cs
For byte1
converted string: AgQGCAoMDhASFA==

bye array is null
Exception Thrown: System.ArgumentNullException

```** 

****例 3:** 为*argumentout of range exception***

```cs
// C# program to demonstrate the
// Convert.ToBase64String() Method
using System;

class GFG {

// Main Method
public static void Main()
{
    try {

        // defining and initializing
        // byte1
        byte[] byte1 = {2, 4, 6, 8, 10,
                   12, 14, 16, 18, 20};

        // calling get() Method
        get(byte1, "byte1");

        Console.WriteLine("");

        // converting base 64 string to byte array
        Console.WriteLine("Length is negative");

        string val = Convert.ToBase64String(byte1, 0, -10);

        Console.WriteLine("Converted byte value: {0}", val);
    }

    catch (ArgumentNullException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }

    catch (ArgumentOutOfRangeException e) {

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
    string val = Convert.ToBase64String(bytes,
                             0, bytes.Length);

    // display the converted string
    Console.WriteLine("converted string: {0}", val);
}
}
```

****Output:**

```cs
For byte1
converted string: AgQGCAoMDhASFA==

Length is negative
Exception Thrown: System.ArgumentOutOfRangeException

```** 

****参考:****

*   **[https://docs . Microsoft . com/en-us/dotnet/API/system . convert . tobase64 string？view = net framework-4 . 7 . 2 # System _ Convert _ tobase64 string _ System _ Byte _ _ _ System _ int 32 _ System _ int 32 _](https://docs.microsoft.com/en-us/dotnet/api/system.convert.tobase64string?view=netframework-4.7.2# System_Convert_ToBase64String_System_Byte___System_Int32_System_Int32_)**