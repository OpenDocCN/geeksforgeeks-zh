# SByte。C# 中的 ToString()方法，带示例| Set–1

> 原文:[https://www . geesforgeks . org/sbyte-tostring-method-in-c-sharp-with-examples-set-1/](https://www.geeksforgeeks.org/sbyte-tostring-method-in-c-sharp-with-examples-set-1/)

**SByte。ToString 方法**用于将当前 SByte 实例的数值转换为其等价的字符串表示形式。该方法的重载列表中有以下 4 种方法:

*   **ToString(表单提供商)方法***   **字符串(字符串，表单提供程序)方法***   **ToString()方法***   **ToString(String) Method

    在这里，我们将讨论前两种方法。

    #### ToString(表单提供商)方法

    此方法用于使用指定的区域性特定格式信息将当前实例的数值转换为其等效的字符串表示形式。

    **语法:**

    ```cs
    public string ToString (IFormatProvider provider);
    ```

    **参数:**该方法获取类型为*的对象，该对象提供特定于区域性的格式信息。*

    **返回值:**此方法以提供程序参数指定的格式返回当前实例值的字符串表示形式。

    **示例:**

    ```cs
    // C# program to demonstrate
    // SByte.ToString(IFormatProvider)
    // Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // declaring and initializing 
            // SByte value
            sbyte s1 = 15;

            // creating and initializing
            // the object of CultureInfo
            CultureInfo provider = new CultureInfo("en-us");

            // Using the method
            string str = s1.ToString(provider);

            // Display the value
            Console.WriteLine("The Value is {0} and provider is {1}",
                                                 str, provider.Name);
        }
    }
    ```

    **Output:**

    ```cs
    The Value is 15 and provider is en-US

    ```

    #### SByte。字符串(字符串，表单提供程序)方法

    此方法用于使用指定的格式和区域性特定的格式信息将此实例的数值转换为其等效的字符串表示形式。

    **语法:**

    ```cs
    public string ToString (string format, IFormatProvider provider);
    ```

    **参数:**

    > **格式:**标准或自定义数字格式字符串。
    > **提供者:**它是一个提供特定于区域性的格式信息的对象。

    **返回值:**该方法返回由*格式*和*提供程序*参数指定的当前实例的字符串表示形式。

    **示例:**

    ```cs
    // C# program to demonstrate the
    // SByte.ToString(String, IFormatProvider)
    // Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {

            // declaring and initializing SByte value
            sbyte s1 = SByte.MaxValue;

            // creating and initializing
            // the object of CultureInfo
            CultureInfo provider = new CultureInfo("fr-FR");

            // declaring and initializing format
            string format = "D5";

            // using the method
            string str = s1.ToString(format, provider);

            // Displaying the details
            Console.WriteLine("The value is {0}", str);
            Console.WriteLine("The Format is {0}", format);
            Console.WriteLine("The Provider is {0}", provider.Name);
        }
    }
    ```

    **Output:**

    ```cs
    The value is 00127
    The Format is D5
    The Provider is fr-FR

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . sbyte . tostring？view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.sbyte.tostring?view=netcore-2.1)**