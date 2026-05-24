# C# | Int32。ToString 方法| Set–2

> 原文:[https://www . geesforgeks . org/c-sharp-int 32-tostring-method-set-2/](https://www.geeksforgeeks.org/c-sharp-int32-tostring-method-set-2/)

**Int32。ToString 方法**用于将当前实例的数值转换为其等价的字符串表示。该方法的重载列表中有以下 4 种方法:

*   **ToString(表单提供商)方法***   **字符串(字符串，表单提供程序)方法***   **ToString()方法***   **ToString(String) Method

    这里我们将讨论最后两种方法。

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
    // Int32.ToString() Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {

            Console.WriteLine("The String values are: ");

            // calling the method
            result(Int32.MaxValue);
            result(Int32.MinValue);
            result(78006596);
            result(86542626);
        }

        // result() method
        public static void result(int p)
        {

            // using ToString() method
            string str = p.ToString();

            // Display the value
            Console.WriteLine("The Corresponding String "+
                                    "Value is: {0}", str);
        }
    }
    ```

    **Output:**

    ```cs
    The String values are: 
    The Corresponding String Value is: 2147483647
    The Corresponding String Value is: -2147483648
    The Corresponding String Value is: 78006596
    The Corresponding String Value is: 86542626

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
    // Int32.ToString(String) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value
                int val = 214563;

                // Declaring and initializing format
                string format = "E2";

                // using the method
                string result = val.ToString(format);

                // Display the result
                Console.WriteLine("The value of string is {0}", result);
            }

            catch (FormatException e) {

                Console.WriteLine("Format is invalid.");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    The value of string is 2.15E+005

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . int 32 . tostring？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int32.tostring?view=netframework-4.7.2)**