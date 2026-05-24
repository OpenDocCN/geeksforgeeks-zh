# C# |字节结构字段

> 原文:[https://www.geeksforgeeks.org/c-sharp-sbyte-struct-fields/](https://www.geeksforgeeks.org/c-sharp-sbyte-struct-fields/)

在 C# 中， ***Sbyte Struct*** 位于*系统*命名空间下，该命名空间表示一个 *8 位*有符号整数。SByte 值类型代表数值范围从 *-128 到+127* 的整数。*系统中有两个字段。字节*结构如下:

*   **SByte。最大值字段***   **SByte.MinValue Field

    #### SByte。最大值字段

    这是一个常量字段，表示最大可能值(127 字节)。

    **语法:**

    ```cs
    public const sbyte MaxValue = 127;
    ```

    **示例:**

    ```cs
    // C# program to demonstrate the SByte.MaxValue
    // Field by checking whether the given +ve long
    // value can be converted to sbyte value or not
    using System;

    class Max_Geeks {

        // Main method
        static public void Main()
        {

            // Only taking +ve values
            long lValue = 128;
            sbyte sbValue;

            // Using the MaxValue Field to check
            // whether the conversion is Possible
            // or not for +ve values only
            if (lValue <= sbyte.MaxValue) {

                // Type conversion from long to sbyte
                sbValue = (sbyte)lValue;

                Console.WriteLine("Converted long integer value to {0}.", sbValue);
            }

            else {
                Console.WriteLine("Conversion is not Possible");
            }
        }
    }
    ```

    **输出:**

    ```cs
    Conversion is not Possible
    ```

    #### SByte。最小值字段

    这是一个常量字段，表示最小可能值(-128)。

    **语法:**

    ```cs
    public const sbyte MinValue = -128;
    ```

    **示例:**

    ```cs
    // C# program to demonstrate the SByte.Min Value
    // Field by checking whether the given -ve long
    // value can be converted to sbyte value or not
    using System;

    class Min_Geeks {

        // Main method
        static public void Main()
        {

            // Only taking -ve values
            long lValue = -128;
            sbyte sbValue;

            // Using the MinValue Field to check
            // whether the conversion is Possible
            // or not for -ve values only
            if (lValue >= sbyte.MinValue) {

                // Type conversion from long to sbyte
                sbValue = (sbyte)lValue;

                Console.WriteLine("Converted long integer value to {0}", sbValue);
            }

            else {
                Console.WriteLine("Conversion is not Possible");
            }
        }
    }
    ```

    **输出:**

    ```cs
    Converted long integer value to -128
    ```

    **参考文献:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . sbyte . maxvalue？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.sbyte.maxvalue?view=netframework-4.7.2)
    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . sbyte . min value？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.sbyte.minvalue?view=netframework-4.7.2)**