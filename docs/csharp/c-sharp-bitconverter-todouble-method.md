# C# | BitConverter。ToDouble()方法

> 原文:[https://www . geesforgeks . org/c-sharp-bit converter-to double-method/](https://www.geeksforgeeks.org/c-sharp-bitconverter-todouble-method/)

**BitConverter。ToDouble()方法**用于返回字节数组中指定位置的八个字节转换而来的双精度浮点数。

**语法:**

```cs
public static double ToDouble (byte[] value, int startIndex);
```

**参数:**

> **值:**是字节数组。
> **起始指数:**是数值内的起始位置。

**返回值:**这个方法返回一个从 startIndex 开始的 8 个字节组成的双精度浮点数。

**异常:**

*   **参数异常:**如果 startIndex 大于或等于值的长度减 7，并且小于或等于值的长度减 1。
*   **ArgumentNullException:** 如果值为空。
*   **argumentoutofrangerexception:**如果 startIndex 小于零或大于值的长度减 1。

以下程序说明了**位转换器的使用。ToDouble(Byte[]，Int32)** 方法:

**例 1:**

```cs
// C# program to demonstrate
// BitConverter.ToDouble(Byte[], Int32)
// Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Define an array of byte values.
        byte[] bytes = {0,0,1,2,7,126,78,55,
                        255,78,45,198,200,1,
                        1,1,1,255,255,2,4,4,
                        77,77,77,77,77,0,1};

        // Display the values of the myArr.
        Console.WriteLine("Initial Array: ");

        // calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(bytes);

        // print char value
        Console.WriteLine("index     Array elements    "+         
                          "              double values");
        Console.WriteLine();

        // getting double value and Display it
        for (int index = 0; index < bytes.Length - 7;
                                index = index + 8) {
            double values = BitConverter.ToDouble(bytes, index);
            Console.WriteLine(" {0}     {1}    {2}", 
                  index, BitConverter.ToString(bytes, 
                                  index, 8), values);
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
    catch (ArgumentException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
}

// Defining the method
// PrintIndexAndValues
public static void PrintIndexAndValues(byte[] myArr)
{
    int count = 0;
    for (int i = 0; i < myArr.Length; i++) {

        if (count == 18) {
            Console.WriteLine();
            Console.Write("{0} ", myArr[i]);
            count = 0;
        }
        else {
            Console.Write("{0} ", myArr[i]);
            count++;
        }
    }

    Console.WriteLine();
    Console.WriteLine();
}
}
```

**输出:**

```cs
Initial Array: 
0 0 1 2 7 126 78 55 255 78 45 198 200 1 1 1 1 255 
255 2 4 4 77 77 77 77 77 0 1 

index     Array elements                  double values

 0     00-00-01-02-07-7E-4E-37    2.73464354303054E-42
 8     FF-4E-2D-C6-C8-01-01-01    7.74999325882041E-304
 16     01-FF-FF-02-04-04-4D-4D    2.38727219494443E+64

```

**示例 2:** 适用于*参数异常*

```cs
// C# program to demonstrate
// BitConverter.ToDouble(Byte[], Int32)
// Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Define an array of byte values.
        byte[] bytes = {0,0,1,2,7,126,78,55,
                        255,78,45,198,200,1,
                        1,1,1,255,255,2,4,4,
                        77,77,77,77,77,0,1,
                        0,0,1,2,7,126,78,55,
                        255,78,45,198,200,1,
                        1,1,1,255,255,2,4,4,
                        255,255,255,255,245,
                        245,245,245,245,245,
                        245,245,245,245,0,0,
                        0,0,0,0,0,0,6,5,6,56,
                        31,31,31,54,23,253,};

        // Display the values of the myArr.
        Console.WriteLine("Initial Array: ");

        // calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(bytes);

        // print char value
        Console.WriteLine("index     Array elements"+
                             "       double values");
        Console.WriteLine();

        // getting double value and Display it
        for (int index = 4; index < bytes.Length - 6; 
                            index = index + 8) {

            if (index == bytes.Length - 7) {
                Console.WriteLine();
                Console.WriteLine("startIndex is equal to"+
                            " the length of bytes minus 7");

                double values = BitConverter.ToDouble(bytes, index);
                Console.WriteLine("  {0}        {1}         {2}", 
                              index, BitConverter.ToString(bytes,
                                              index, 4), values);
            }
            else {
                double values = BitConverter.ToDouble(bytes, index);
                Console.WriteLine("  {0}        {1}         {2}",
                       index, BitConverter.ToString(bytes, index,
                                                     8), values);
            }
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
    catch (ArgumentException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
}

// Defining the method
// PrintIndexAndValues
public static void PrintIndexAndValues(byte[] myArr)
{
    int count = 0;
    for (int i = 0; i < myArr.Length; i++) {

        if (count == 18) {
            Console.WriteLine();
            Console.Write("{0} ", myArr[i]);
            count = 0;
        }
        else {
            Console.Write("{0} ", myArr[i]);
            count++;
        }
    }

    Console.WriteLine();
    Console.WriteLine();
}
}
```

**输出:**

```cs
Initial Array: 
0 0 1 2 7 126 78 55 255 78 45 198 200 1 1 1 1 255 
255 2 4 4 77 77 77 77 77 0 1 0 0 1 2 7 126 78 55 
255 78 45 198 200 1 1 1 1 255 255 2 4 4 255 255 255 255 245 
245 245 245 245 245 245 245 245 245 0 0 0 0 0 0 0 0 6 5 
6 56 31 31 31 54 23 253 

index        Array elements                    double values

  4        07-7E-4E-37-FF-4E-2D-C6         -1.16103254047091E+30
  12        C8-01-01-01-01-FF-FF-02         3.13113229681351E-294
  20        04-04-4D-4D-4D-4D-4D-00         3.25995134720157E-307
  28        01-00-00-01-02-07-7E-4E         1.29525825666467E+70
  36        37-FF-4E-2D-C6-C8-01-01         8.10420695824091E-304
  44        01-01-FF-FF-02-04-04-FF         -6.86302832487538E+303
  52        FF-FF-FF-F5-F5-F5-F5-F5         -1.68827860814431E+260
  60        F5-F5-F5-F5-F5-00-00-00         5.21927749055768E-312
  68        00-00-00-00-00-06-05-06         1.15818454395586E-279

startIndex is equal to the length of bytes minus 7
Exception Thrown: System.ArgumentException

```

**例 3:** 为*argumentout of range exception*

```cs
// C# program to demonstrate
// BitConverter.ToDouble(Byte[], Int32)
// Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Define an array of byte values.
        byte[] bytes = {0,0,1,2,7,126,78,55,
                    255,78,45,198,200,1,
                    1,1,1,255,255,2,4,4,
                    77,77,77,77,77,0,1,
                    0,0,1,2,7,126,78,55,
                    255,78,45,198,200,1,
                    1,1,1,255,255,2,4,4,
                    255,255,255,255,245,
                    245,245,245,245,245,
                    245,245,245,245,0,0,
                    0,0,0,0,0,0,6,5,6,56,
                    31,31,31,54,23,253,};

        // Display the values of the myArr.
        Console.WriteLine("Initial Array: ");

        // calling the PrintIndexAndValues()
        // method to print
        PrintIndexAndValues(bytes);

        // getting double value and Display it
        Console.WriteLine("startIndex is less than zero");
        double values = BitConverter.ToDouble(bytes, -1);
        Console.WriteLine(" {0}     {1}         {2}", -1,
                 BitConverter.ToString(bytes, -1, 8),
                                             values);
    }
    catch (ArgumentNullException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
    catch (ArgumentOutOfRangeException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
    catch (ArgumentException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
}

// Defining the method
// PrintIndexAndValues
public static void PrintIndexAndValues(byte[] myArr)
{
    int count = 0;
    for (int i = 0; i < myArr.Length; i++) {

        if (count == 18) {
            Console.WriteLine();
            Console.Write("{0} ", myArr[i]);
            count = 0;
        }
        else {
            Console.Write("{0} ", myArr[i]);
            count++;
        }
    }

    Console.WriteLine();
    Console.WriteLine();
}
}
```

**输出:**

```cs
Initial Array: 
0 0 1 2 7 126 78 55 255 78 45 198 200 1 1 1 1 255 
255 2 4 4 77 77 77 77 77 0 1 0 0 1 2 7 126 78 55 
255 78 45 198 200 1 1 1 1 255 255 2 4 4 255 255 255 255 245 
245 245 245 245 245 245 245 245 245 0 0 0 0 0 0 0 0 6 5 
6 56 31 31 31 54 23 253 

startIndex is less than zero
Exception Thrown: System.ArgumentOutOfRangeException

```

**示例 4:** 适用于*参数异常*

```cs
// C# program to demonstrate
// BitConverter.ToDouble(Byte[], Int32)
// Method
using System;

class GFG {

// Main Method
public static void Main()
{

    try {

        // Define an array of byte values.
        byte[] bytes = null;

        // getting double value and Display it
        Console.WriteLine("array bytes is null");
        double values = BitConverter.ToDouble(bytes, 0);
        Console.WriteLine(" {0}     {1}         {2}", 0,
          BitConverter.ToString(bytes, 0, 8), values);
    }
    catch (ArgumentNullException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
    catch (ArgumentOutOfRangeException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
    catch (ArgumentException e) {

        Console.Write("Exception Thrown: ");
        Console.Write("{0}", e.GetType(), e.Message);
    }
}

// Defining the method
// PrintIndexAndValues
public static void PrintIndexAndValues(byte[] myArr)
{
    int count = 0;
    for (int i = 0; i < myArr.Length; i++) {

        if (count == 18) {
            Console.WriteLine();
            Console.Write("{0} ", myArr[i]);
            count = 0;
        }
        else {
            Console.Write("{0} ", myArr[i]);
            count++;
        }
    }

    Console.WriteLine();
    Console.WriteLine();
}
}
```

**输出:**

```cs
array bytes is null
Exception Thrown: System.ArgumentNullException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . bit converter . to double？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.bitconverter.todouble?view=netframework-4.7.2)