# C# |数学。Abs()方法|设置–1

> 原文:[https://www . geesforgeks . org/c-sharp-math-ABS-method-set-1/](https://www.geeksforgeeks.org/c-sharp-math-abs-method-set-1/)

在 C# 中，***【Abs()***是一个 Math 类方法，用来返回指定数字的绝对值。这个方法可以通过传递不同类型的参数来重载。

2.  **[数学。Abs(十进制)](# Math.Abs(Decimal))**
3.  **[数学。Abs(双)](# Math.Abs(Double))**
4.  **[数学。Abs(Int16)](# Math.Abs(Int16))**
5.  **[数学。Abs(Int32)](# Math.Abs(Int32))**
6.  **数学。Abs(Int64)**
7.  **Math.Abs(SByte)**
8.  **Math.Abs(Single)

    #### 数学。Abs(十进制)

    此方法用于返回十进制数的绝对值。

    **语法:**

    ```cs
    public static decimal Abs (decimal val);
    ```

    **参数:**

    > **val:** 是大于等于*小数的必选数字。最小值*，但小于或等于*小数。*型系统的最大值*。小数*。

    **返回类型:**返回一个十进制数，比如说 *r* ，这样 *0 ≤ r ≤十进制。最大值*。

    **示例:**

    ```cs
    // C# Program to illlustrate the
    // Math.Abs(Decimal) Method
    using System;

    class Geeks {

        // Main Method
        public static void Main()
        {

            // Taking decimal values
            decimal[] deci = {Decimal.MinValue, 45.14M, 0M,
                                -17.47M, Decimal.MaxValue};

            // using foreach loop
            foreach(decimal value in deci)

                // Displaying the result
                Console.WriteLine("Absolute value of {0} = {1}",
                                        value, Math.Abs(value));
        }
    }
    ```

    **输出:**

    ```cs
    Absolute value of -79228162514264337593543950335 = 79228162514264337593543950335
    Absolute value of 45.14 = 45.14
    Absolute value of 0 = 0
    Absolute value of -17.47 = 17.47
    Absolute value of 79228162514264337593543950335 = 79228162514264337593543950335

    ```

    #### 数学。腹肌(双)

    此方法用于返回双精度浮点数的绝对值。

    **语法:**

    ```cs
    public static double Abs (double val);
    ```

    **参数:**

    > **val:** 是大于等于 *Double 的必选项。MinValue* ，但小于等于*翻倍。*型系统的最大值*。双*。

    **返回类型:**返回一个双精度浮点数，比如说 *r* ，这样 *0 ≤ r ≤ Double。最大值*。

    **注:**

    *   如果*值*等于*负有限性*或*正有限性*，返回值将为*正有限性*。
    *   如果*值*等于 *NaN* ，则返回值为 *NaN* 。

    **示例:**

    ```cs
    // C# Program to illlustrate the
    // Math.Abs(Double) Method
    using System;

    class Geeks {

        // Main Method
        public static void Main()
        {

            // Taking a NaN
            Double nan = Double.NaN;

            // Taking double values
            double[] doub = {Double.MinValue, 27.58, 0.0,
                            56.48e10, nan, Double.MaxValue};

            // using foreach loop
            foreach(double value in doub)

                // Displaying the result
                Console.WriteLine("Absolute value of {0} = {1}",
                                        value, Math.Abs(value));
        }
    }
    ```

    **输出:**

    ```cs
    Absolute value of -1.79769313486232E+308 = 1.79769313486232E+308
    Absolute value of 27.58 = 27.58
    Absolute value of 0 = 0
    Absolute value of 564800000000 = 564800000000
    Absolute value of NaN = NaN
    Absolute value of 1.79769313486232E+308 = 1.79769313486232E+308

    ```

    #### 数学。Abs(Int16)

    此方法用于返回 16 位有符号整数的绝对值。

    **语法:**

    ```cs
    public static short Abs (short val);
    ```

    **参数:**

    > **val:** 是大于 *Int16 的必选数字。最小值*，但小于或等于 *Int16。*型系统的最大值*。Int16* 。

    **返回类型:**返回 16 位有符号整数，比如说 *r* ，这样 *0 ≤ r ≤ Int16。最大值*。

    **异常:**如果*值*等于 *Int16，此方法将给出**overoveroverowexception**。MinValue* 。

    **示例:**

    ```cs
    // C# Program to illlustrate the
    // Math.Abs(Int16) Method
    using System;

    class Geeks {

        // Main Method
        public static void Main()
        {

            // Taking short values
            short[] sh = {Int16.MaxValue, 1482, -142, 0 };

            // using foreach loop
            foreach(short value in sh)

                // Displaying the result
                Console.WriteLine("Absolute value of {0} = {1}",
                                        value, Math.Abs(value));
        }
    }
    ```

    **输出:**

    ```cs
    Absolute value of 32767 = 32767
    Absolute value of 1482 = 1482
    Absolute value of -142 = 142
    Absolute value of 0 = 0

    ```

    #### 数学。Abs(Int32)

    此方法用于返回 32 位有符号整数的绝对值。

    **语法:**

    ```cs
    public static int Abs (int val);
    ```

    **参数:**

    > **val:** 是大于 *Int32 的必选数字。最小值*，但小于或等于 *Int32。*型系统的最大值*。Int32* 。

    **返回类型:**返回 32 位有符号整数，比如说 *r* ，这样 *0 ≤ r ≤ Int32。最大值*。

    **异常:**如果*值*等于 *Int32，此方法将给出**overoveroverowexception**。MinValue* 。

    **示例:**

    ```cs
    // C# Program to illlustrate the
    // Math.Abs(Int32) Method
    using System;

    class Geeks {

        // Main Method
        public static void Main()
        {

            // Taking int values
            int[] int_val = {Int32.MaxValue, 13482, -65525, 0};

            // using foreach loop
            foreach(int value in int_val)

                // Displaying the result
                Console.WriteLine("Absolute value of {0} = {1}",
                                        value, Math.Abs(value));
        }
    }
    ```

    **输出:**

    ```cs
    Absolute value of 2147483647 = 2147483647
    Absolute value of 13482 = 13482
    Absolute value of -65525 = 65525
    Absolute value of 0 = 0

    ```

    它的重载列表中总共有 7 个方法。这里只讨论前 4 种方法，其余 3 种方法在 *[C# | Math 中讨论。Abs()方法|设置–2](https://www.geeksforgeeks.org/c-math-abs-method-set-2/)*。

    **参考:**[https://docs . Microsoft . com/en-us/dotnet/API/system . math . ABS？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.math.abs?view=netframework-4.7.2)**