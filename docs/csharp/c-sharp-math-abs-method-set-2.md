# C# |数学。Abs()方法|设置–2

> 原文:[https://www . geesforgeks . org/c-sharp-math-ABS-method-set-2/](https://www.geeksforgeeks.org/c-sharp-math-abs-method-set-2/)

[C# |数学。Abs()方法|设置–1](https://www.geeksforgeeks.org/c-math-abs-method-set-1/)

在 C# 中，***【Abs()***是一个 Math 类方法，用来返回指定数字的绝对值。这个方法可以通过传递不同类型的参数来重载。它的重载列表中总共有 7 个方法。

2.  **数学。Abs(十进制)**
3.  **数学。腹肌(双)**
4.  **数学。Abs(Int16)**
5.  **数学。Abs(Int32)**
6.  **[数学。Abs(Int64)](# Math.Abs(Int64))**
7.  **[数学. Abs(SByte)](# Math.Abs(SByte))**
8.  **[Math.Abs(Single)](# Math.Abs(Single))

    #### 数学。Abs(Int64)

    此方法用于返回 64 位有符号整数的绝对值。

    **语法:**

    ```cs
    public static long Abs (long val);
    ```

    **参数:**

    > **val:** 是大于 *Int64 的必选数字。最小值*，但小于或等于 *Int64。*型系统的最大值*。Int64* 。

    **返回类型:**返回一个 64 位有符号整数，比如说 *r* ，这样 *0 ≤ r ≤ Int64。最大值*。

    **异常:**如果*值*等于 *Int64，此方法将给出**overoverowexception**。MinValue* 。

    **示例:**

    ```cs
    // C# Program to illustrate the
    // Math.Abs(Int64) Method
    using System;

    class Geeks {

        // Main Method
        public static void Main()
        {

            // Taking long values
            long[] val = {Int64.MaxValue, 78345482, -4687985, 0};

            // using foreach loop
            foreach(long value in val)

                // Displaying the result
                Console.WriteLine("Absolute value of {0} = {1}",
                                        value, Math.Abs(value));
        }
    }
    ```

    **输出:**

    ```cs
    Absolute value of 9223372036854775807 = 9223372036854775807
    Absolute value of 78345482 = 78345482
    Absolute value of -4687985 = 4687985
    Absolute value of 0 = 0

    ```

    #### Math.Abs(SByte)

    此方法用于返回 8 位有符号整数的绝对值。

    **语法:**

    ```cs
    public static sbyte Abs (sbyte val);
    ```

    **参数:**

    > **val:** 是大于 *SByte 的要求数。最小值*，但小于或等于*字节。*型系统的最大值*。SByte* 。

    **返回类型:**返回一个 8 位有符号整数，比如说 *r* ，这样 *0 ≤ r ≤ SByte。最大值*。

    **异常:**如果*值*等于*字节，此方法将给出**溢出异常**。MinValue* 。

    **示例:**

    ```cs
    // C# Program to illlustrate the
    // Math.Abs(SByte) Method
    using System;

    class Geeks {

        // Main Method
        public static void Main()
        {

            // Taking SByte values
            sbyte[] sb = {SByte.MaxValue, 45, -41, 0};

            // using foreach loop
            foreach(sbyte value in sb)

                // Displaying the result
                Console.WriteLine("Absolute value of {0} = {1}",
                                        value, Math.Abs(value));
        }
    }
    ```

    **输出:**

    ```cs
    Absolute value of 127 = 127
    Absolute value of 45 = 45
    Absolute value of -41 = 41
    Absolute value of 0 = 0

    ```

    #### 数学。Abs(单个)

    此方法用于返回单精度浮点数的绝对值。

    **语法:**

    ```cs
    public static float Abs (float val);
    ```

    **参数:**

    > **val:** 是大于等于 *Single 的必选数字。最小值*，但小于或等于类型*系统的最大值。单*。

    **返回类型:**返回一个单精度浮点数，比如说 *r* ，这样 *0 ≤ r ≤ Single。最大值*。

    **注:**

    *   如果*值*等于*负有限性*或*正有限性*，返回值将为*正有限性*。
    *   如果*值*等于 *NaN* ，则返回值为 *NaN* 。

    **示例:**

    ```cs
    // C# Program to illlustrate the
    // Math.Abs(Single) Method
    using System;

    class Geeks {

        // Main Method
        public static void Main()
        {

            float nan = float.NaN;

            // Taking float values
            float[] fl = {float.MinValue, 127.58f, 0.000f,
                        7556.48e10f, nan, float.MaxValue};

            // using foreach loop
            foreach(float value in fl)

                // Displaying the result
                Console.WriteLine("Absolute value of {0} = {1}",
                                        value, Math.Abs(value));
        }
    }
    ```

    **输出:**

    ```cs
    Absolute value of -3.402823E+38 = 3.402823E+38
    Absolute value of 127.58 = 127.58
    Absolute value of 0 = 0
    Absolute value of 7.55648E+13 = 7.55648E+13
    Absolute value of NaN = NaN
    Absolute value of 3.402823E+38 = 3.402823E+38

    ```

    **参考:**[https://docs . Microsoft . com/en-us/dotnet/API/system . math . ABS？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.math.abs?view=netframework-4.7.2)**