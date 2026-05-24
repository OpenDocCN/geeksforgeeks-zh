# SByte。C# 中的 ToString 方法，带示例| Set–2

> 原文:[https://www . geesforgeks . org/sbyte-tostring-method-in-c-sharp-with-examples-set-2/](https://www.geeksforgeeks.org/sbyte-tostring-method-in-c-sharp-with-examples-set-2/)

**SByte。ToString 方法**用于将当前实例的数值转换为其等价的字符串表示。该方法的重载列表中有以下 4 种方法:

*   **ToString(表单提供商)方法***   **字符串(字符串，表单提供程序)方法***   **ToString()方法***   **ToString(String) Method

    在这里，我们将讨论最后两种方法。

    #### ToString()方法

    此方法用于将当前实例的数值转换为其等效的字符串表示形式。

    **语法:**

    ```cs
    public override string ToString ();
    ```

    **返回值:**此方法返回当前实例值的字符串表示形式，如果值为负，则由减号和 0 到 9 之间的数字序列组成，没有前导零。

    **示例:**

    ```cs
    // C# program to illustrate the
    // SByte.ToString() Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {

            Console.WriteLine("The String values are: ");

            // calling the method
            result(SByte.MaxValue);
            result(SByte.MinValue);
            result(120);
            result(86);
        }

        // result() method
        public static void result(sbyte p)
        {

            // using ToString() method
            string str = p.ToString();

            // Display the value
            Console.WriteLine("The Corresponding String "
                                  + "Value is: {0}",str);

        }
    }
    ```

    **Output:**

    ```cs
    The String values are: 
    The Corresponding String Value is: 127
    The Corresponding String Value is: -128
    The Corresponding String Value is: 120
    The Corresponding String Value is: 86

    ```

    #### 字符串方法

    此方法用于使用指定的格式将当前实例的数值转换为其等效的字符串表示形式。

    **语法:**

    ```cs
    public string ToString (string format);
    ```

    **参数:**此方法采用标准或自定义数字格式字符串。

    **返回值:**该方法返回由格式指定的该实例的值的字符串表示形式。

    **示例:**

    ```cs
    // C# program to demonstrate the
    // SByte.ToString(String) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value
                sbyte val = 114;

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
    The value of string is 1.14E+002

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . sbyte . tostring？view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.sbyte.tostring?view=netcore-2.1)**