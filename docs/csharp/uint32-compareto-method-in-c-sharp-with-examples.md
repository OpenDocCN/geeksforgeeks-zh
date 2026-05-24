# UInt32。将 C# 中的()方法与示例进行比较

> 原文:[https://www . geeksforgeeks . org/uint 32-compare to-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint32-compareto-method-in-c-sharp-with-examples/)

**UInt32。比较方法**用于将当前实例与指定对象或另一个 *UInt32* 实例进行比较。它返回一个整数，该整数显示当前实例的值是小于、等于还是大于指定对象或其他 UInt32 实例的值。此方法的重载列表中有 2 种方法，如下所示:

*   **比较(UInt32)方法***   **CompareTo(Object) Method

    #### UInt32。比较(UInt32)方法

    此方法用于将当前实例与指定的 32 位无符号整数进行比较，并返回一个整数，该整数显示当前实例的值是小于、等于还是大于指定的 32 位无符号整数的值。

    **语法:**

    ```cs
    public int CompareTo (uint value);
    ```

    这里，需要一个无符号整数来进行比较。

    **返回值:**返回一个 32 位有符号数，表示当前实例和*值*参数的相对值，如下所示:

    *   **小于零:**如果当前实例<值
    *   **如果当前实例=值，则为零:**
    *   **大于零:**如果当前实例>值

    以下程序说明了 *UInt32 的使用。*比较法

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // UInt32.CompareTo(UInt32) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {

            // Declaring and initializing value1
            uint value1 = 1231;

            // Declaring and initializing value2
            uint value2 = 5123;

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
    1231 is less than 5123

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // UInt32.CompareTo(UInt32) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            // calling get() method
            get(34425, 7343);
            get(340, 67520);
            get(7810, 2890);
            get(700, 700);
        }

        // defining get() method
        public static void get(uint value1,
                               uint value2)
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
    34425 is greater than 7343
    340 is less than 67520
    7810 is greater than 2890
    700 is equal to 700

    ```

    #### UInt32。比较对象方法

    此方法用于将当前实例与指定的对象进行比较，并返回一个整数，该整数指示当前实例的值是小于、等于还是大于对象的值。

    **语法:**

    ```cs
    public int CompareTo (object value);
    ```

    这里，它将对象与这个实例进行比较，或者为 null。

    **返回值:**返回一个 32 位有符号数，表示当前实例和*值*参数的相对值，如下所示:

    *   **小于零:**如果当前实例<值
    *   **如果当前实例=值，则为零:**
    *   **大于零:**如果当前实例>值

    **异常:**如果*值*不是 *UInt32* ，则抛出*参数异常*。

    以下程序说明了 *UInt32 的使用。比较(对象)*方法

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // UInt32.CompareTo(Object) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value1
                uint value1 = 11220;

                // Declaring and initializing value2
                object value2 = (uint)2347.84376;

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
                Console.WriteLine("value2 must be null"+
                           " or an instance of UInt32");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    11220 is greater than 2347

    ```

    **示例 2:** 适用于*参数异常*

    ```cs
    // C# program to demonstrate the
    // UInt32.CompareTo(Object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value1
                uint value1 = 1790;

                // Declaring and initializing value2
                object value2 = 1 / 7;

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
                Console.WriteLine("value2 must be null"+
                           " or an instance of UInt32");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    value2 must be null or an instance of UInt32
    Exception Thrown: System.ArgumentException

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . uint 32 . compare to？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint32.compareto?view=netstandard-2.1)**