# SByte。将 C# 中的()方法与示例进行比较

> 原文:[https://www . geesforgeks . org/sbyte-compare to-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/sbyte-compareto-method-in-c-sharp-with-examples/)

SByte。方法用于将当前实例与指定的对象或字节进行比较，并返回它们相对值的指示。此方法的重载列表中有 2 种方法，如下所示:

*   **比较法***   **CompareTo(Object) Method

    #### SByte。比较法

    此方法用于将当前实例与指定的 8 位有符号整数进行比较，并返回其相对值的指示。

    **语法:**

    ```cs
    public int CompareTo (sbyte value);
    ```

    这里，它使用 8 位有符号整数与当前实例进行比较。

    **返回值:**返回一个 32 位有符号数，表示当前实例和*值*参数的相对值，如下所示:

    *   **小于零:**如果当前实例<值
    *   **如果当前实例=值，则为零:**
    *   **大于零:**如果当前实例>值

    下面的程序说明了 *SByte 的使用。*方法:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // SByte.CompareTo(SByte) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {

            // Declaring and initializing value1
            sbyte value1 = 10;

            // Declaring and initializing value2
            sbyte value2 = 20;

            // compare both SByte value
            // using CompareTo() method
            int status = value1.CompareTo(value2);

            // checking the status
            if (status > 0)
                Console.WriteLine("{0} is greater than {1}",
                                            value1, value2);
            else if (status < 0)
                Console.WriteLine("{0} is less than {1}",
                                          value1, value2);
            else
                Console.WriteLine("{0} is equal to {1}",
                                        value1, value2);
        }
    }
    ```

    **Output:**

    ```cs
    10 is less than 20

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // SByte.CompareTo(SByte) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            // calling get() method
            get(5, 7);
            get(30, 20);
            get(10, 20);
            get(7, -12);
        }

        // defining get() method
        public static void get(sbyte value1,
                               sbyte value2)
        {

            // using CompareTo() method
            int status = value1.CompareTo(value2);

            // checking the status
            if (status > 0)
                Console.WriteLine("{0} is greater than {1}",
                                            value1, value2);
            else if (status < 0)
                Console.WriteLine("{0} is less than {1}",
                                         value1, value2);
            else
                Console.WriteLine("{0} is equal to {1}",
                                        value1, value2);
        }
    }
    ```

    **Output:**

    ```cs
    5 is less than 7
    30 is greater than 20
    10 is less than 20
    7 is greater than -12

    ```

    #### SByte。比较对象方法

    此方法用于将当前实例与指定对象进行比较，并返回它们相对值的比较结果。

    **语法:**

    ```cs
    public int CompareTo (object value);
    ```

    这里，它将对象与这个实例进行比较，或者为 null。

    **返回值:**返回一个 32 位有符号数，表示当前实例和*值*参数的相对值，如下所示:

    *   **小于零:**如果当前实例<值
    *   **如果当前实例=值，则为零:**
    *   **大于零:**如果当前实例>值

    **异常:**如果值不是*字节*，则抛出*参数异常*。

    下面的程序说明了*小数的使用。比较(对象)*方法

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // SByte.CompareTo(object) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value1
                sbyte value1 = 10;

                // Declaring and initializing value2
                // explicit type casting the value 9
                object value2 = (sbyte)9;

                // compare both sbyte value
                // using CompareTo() method
                int status = value1.CompareTo(value2);

                // checking the status
                if (status > 0)
                    Console.WriteLine("{0} is greater than {1}",
                                                value1, value2);

                else if (status < 0)
                    Console.WriteLine("{0} is less than {1}",
                                             value1, value2);
                else
                    Console.WriteLine("{0} is equal to {1}",
                                            value1, value2);
            }

            catch (ArgumentException e) 
            {
                Console.WriteLine("value2 must be SByte");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    10 is greater than 9

    ```

    **示例 2:** 适用于*参数异常*

    ```cs
    // C# program to demonstrate the
    // SByte.CompareTo(object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value1
                sbyte value1 = 10;

                // Declaring and initializing value2
                object value2 = 1 / 3;

                // using CompareTo() method
                int status = value1.CompareTo(value2);

                // checking the status
                if (status > 0)
                    Console.WriteLine("{0} is greater than {1}",
                                                value1, value2);

                else if (status < 0)
                    Console.WriteLine("{0} is less than {1}",
                                             value1, value2);
                else
                    Console.WriteLine("{0} is equal to {1}",
                                            value1, value2);
            }

            catch (ArgumentException e) 
            {
                Console.WriteLine("value2 must be sbyte");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    value2 must be sbyte
    Exception Thrown: System.ArgumentException

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . sbyte . compare to？view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.sbyte.compareto?view=netcore-2.1)**