# UInt32。C# 中的 ToString 方法，带示例| Set–2

> 原文:[https://www . geesforgeks . org/uint 32-tostring-method-in-c-sharp-with-examples-set-2/](https://www.geeksforgeeks.org/uint32-tostring-method-in-c-sharp-with-examples-set-2/)

**UInt32。ToString 方法**用于将当前实例的数值转换为其等价的字符串表示。该方法的重载列表中有以下 4 种方法:

*   **ToString(表单提供商)方法***   **字符串(字符串，表单提供程序)方法***   **ToString()方法***   **ToString(String) Method

    在这里，我们将讨论最后两种方法。

    #### ToString()方法

    此方法用于将当前实例的数值转换为其等效的字符串表示形式。

    **语法:**

    ```cs
    public override string ToString ();
    ```

    **返回值:**此方法返回当前实例值的字符串表示形式，由 0 到 9 的数字序列组成，不带符号或前导零。

    **示例:**

    ```cs
    // C# program to illustrate the
    // UInt32.ToString() Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {

            Console.WriteLine("The String values are: ");

            // calling the method
            result(UInt32.MaxValue);
            result(UInt32.MinValue);
            result(155156);
            result(199947);
        }

        // result() method
        public static void result(uint p)
        {

            // using ToString() method
            string str = p.ToString();

            // Display the value
            Console.WriteLine("The Corresponding String "
                                 + "Value is: {0}", str);

        }
    }
    ```

    **Output:**

    ```cs
    The String values are: 
    The Corresponding String Value is: 4294967295
    The Corresponding String Value is: 0
    The Corresponding String Value is: 155156
    The Corresponding String Value is: 199947

    ```

    #### 字符串方法

    此方法用于使用指定的格式将当前实例的数值转换为其等效的字符串表示形式。

    **语法:**

    ```cs
    public string ToString (string format);
    ```

    **参数:**该方法取数值格式字符串。

    **返回值:**该方法返回由格式指定的该实例的值的字符串表示形式。

    **异常:**如果*格式*参数无效，此方法将给出*格式异常*。

    **示例:**

    ```cs
    // C# program to demonstrate the
    // UInt32.ToString(String) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value
                uint val = 151256;

                // Declaring and initializing format
                string format = "E2";

                // using the method
                string result = val.ToString(format);

                // Display the result
                Console.WriteLine("The value of string is {0}", result);
            }

            catch (FormatException e) 
            {
                Console.WriteLine("Format is invalid.");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    The value of string is 1.51E+005

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . uint 32 . tostring？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint32.tostring?view=netstandard-2.1)**