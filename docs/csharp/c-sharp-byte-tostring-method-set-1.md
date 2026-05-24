# C# | Byte。ToString 方法|设置–1

> 原文:[https://www . geesforgeks . org/c-sharp-byte-tostring-method-set-1/](https://www.geeksforgeeks.org/c-sharp-byte-tostring-method-set-1/)

此方法用于将当前字节对象的值转换为其等效的字符串表示形式。*字节的重载列表中总共有 4 种方法。ToString()方法*如下:

*   **ToString(文件格式提供程序)***   **ToString(字符串文件格式提供程序)***   **ToString()***   **ToString(String)

    #### ToString(文件格式提供程序)

    此方法用于使用指定的区域性特定格式信息将当前字节对象的数值转换为其等效的字符串表示形式。

    **语法:**

    ```cs
    public string ToString (IFormatProvider provider);
    ```

    **参数:**该方法采用类型为*的对象，该对象提供特定于区域性的格式信息。*

    **返回值:**此方法以提供程序参数指定的格式返回此对象值的字符串表示形式。

    以下程序说明了**字节的使用。**方法:

    **例 1:**

    ```cs
    // C# program to demonstrate
    // Byte.ToString(IFormatProvider)
    // Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // declaring and initializing bytevalue
            byte byteValue = 15;

            // creating and initializing 
            // the object of CultureInfo
            CultureInfo provider = new CultureInfo("en-us");

            // getting the value
            // using ToString()
            string value = byteValue.ToString(provider);

            // Display the value
            Console.WriteLine("value is {0} and provider is {1}",
                                           value, provider.Name);
        }
    }
    ```

    **Output:**

    ```cs
    value is 15 and provider is en-US

    ```

    #### 字节。字符串(字符串，表单提供程序)方法

    此方法用于使用指定的格式和区域性特定的格式信息将当前字节对象的值转换为其等效的字符串表示形式。

    **语法:**

    ```cs
    public string ToString (string format, IFormatProvider provider);
    ```

    **参数:**

    > **格式:**标准或自定义数字格式字符串。
    > **提供程序:**它是一个提供区域性特定格式信息的对象。

    **返回值:**此方法以提供程序参数指定的格式返回此对象值的字符串表示形式。

    **异常:**如果格式包含不支持的说明符，此方法将给出*格式异常*。

    以下程序说明了**字节的使用。**方法:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Byte.ToString(String, IFormatProvider)
    // Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {

            // declaring and initializing bytevalue
            byte byteValue = 15;

            // creating and initializing 
            // the object of CultureInfo
            CultureInfo provider = new CultureInfo("fr-FR");

            // declaring and initializing format
            string format = "D5";

            // getting the value
            // using ToString()
            string value = byteValue.ToString(format, provider);

            // Display the value
            Console.WriteLine("value is {0} and provider is {1}",
                                          value, provider.Name);
        }
    }
    ```

    **Output:**

    ```cs
    value is 00015 and provider is fr-FR

    ```

    **例 2:** 为*格式异常*

    ```cs
    // C# program to demonstrate the
    // Byte.ToString(String, IFormatProvider)
    // Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {

            try {

                // declaring and initializing bytevalue
                byte byteValue = 15;

                // creating and initializing
                // the object of CultureInfo
                CultureInfo provider = new CultureInfo("fr-FR");

                // declaring and initializing format
                string format = "s5";

                // getting the value
                // using ToString()
                Console.WriteLine("format is invalid");
                string value = byteValue.ToString(format, provider);

                // Display the value
                Console.WriteLine("value is {0} and provider is {1}",
                                               value, provider.Name);
            }
            catch (FormatException e) {

                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    format is invalid
    Exception Thrown: System.FormatException

    ```

    #### 字节。ToString()方法

    此方法用于将当前字节对象的值转换为其等效的字符串表示形式。

    **语法:**

    ```cs
    public override string ToString ();
    ```

    **返回值:**这个方法返回这个对象的值的字符串表示形式，它由 0 到 9 的数字序列组成，没有前导零。

    以下程序说明了**字节的使用。ToString()方法**:

    **例 1:**

    ```cs
    // C# program to demonstrate
    // Byte.ToString() Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {

            // declaring and initializing bytevalue
            byte byteValue = 15;

            // getting the value
            // using ToString()
            string value = byteValue.ToString();

            // Display the value
            Console.WriteLine("value is {0} ", value);
        }
    }
    ```

    **Output:**

    ```cs
    value is 15

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . byte . tostring？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.byte.tostring?view=netframework-4.7.2)**