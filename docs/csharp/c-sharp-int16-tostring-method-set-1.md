# C# | Int16。ToString 方法|设置–1

> 原文:[https://www . geesforgeks . org/c-sharp-int 16-tostring-method-set-1/](https://www.geeksforgeeks.org/c-sharp-int16-tostring-method-set-1/)

**Int16。ToString 方法**用于将当前实例的数值转换为其等价的字符串表示。该方法的重载列表中有以下 4 种方法:

*   **ToString(表单提供商)方法***   **字符串(字符串，表单提供程序)方法***   **ToString()方法***   **ToString(String) Method

    这里我们将讨论前两种方法。

    #### ToString(表单提供商)方法

    此方法用于使用指定的区域性特定格式信息将此实例的数值转换为其等效的字符串表示形式。

    **语法:**

    ```cs
    public string ToString (IFormatProvider provider);
    ```

    **参数:**该方法获取类型为*的对象，该对象提供特定于区域性的格式信息。*

    **返回值:**此方法以提供程序参数指定的格式返回当前对象值的字符串表示形式。

    **示例:**

    ```cs
    // C# program to demonstrate
    // Int16.ToString(IFormatProvider)
    // Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // declaring and initializing
            // Int16 value
            short s1 = 15;

            // creating and initializing
            // the object of CultureInfo
            CultureInfo provider = new CultureInfo("en-us");

            // using the method
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

    #### Int16。字符串(字符串，表单提供程序)方法

    此方法用于使用指定的格式和区域性特定的格式信息将此实例的数值转换为其等效的字符串表示形式。

    > **语法:**公共字符串 ToString(字符串格式，IFormatProvider 提供程序)；
    > 
    > **参数:**
    > **格式:**是一个数字格式的字符串。
    > **提供程序:**它是一个提供区域性特定格式信息的对象。
    > 
    > **返回值:**该方法返回当前实例值的字符串表示形式，由*格式*和*提供程序*指定。

    **示例:**

    ```cs
    // C# program to demonstrate the
    // Int16.ToString(String, IFormatProvider)
    // Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {

            // declaring and initializing
            // Int16 value
            short s1 = 99;

            // creating and initializing
            // the object of CultureInfo
            CultureInfo provider = new CultureInfo("fr-FR");

            // declaring and initializing format
            string format = "D5";

            // using the method
            string str = s1.ToString(format, provider);

            // Displaying the details
            Console.WriteLine("The value is {0}",str);
            Console.WriteLine("The Format is {0}",format);
            Console.WriteLine("The Provider is {0}", provider.Name);
        }
    }
    ```

    **Output:**

    ```cs
    The value is 00099
    The Format is D5
    The Provider is fr-FR

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . int 16 . tostring？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int16.tostring?view=netframework-4.7.2)**