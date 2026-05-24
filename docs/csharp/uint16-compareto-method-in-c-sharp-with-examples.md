# UInt16。将 C# 中的()方法与示例进行比较

> 原文:[https://www . geeksforgeeks . org/uint 16-compare to-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint16-compareto-method-in-c-sharp-with-examples/)

**UInt16。比较方法**用于将当前实例与指定对象或另一个 *UInt16* 实例进行比较。它返回一个整数，该整数显示当前实例的值是小于、等于还是大于指定对象或其他 UInt16 实例的值。此方法的重载列表中有 2 种方法，如下所示:

*   **比较(UInt16)方法***   **CompareTo(Object) Method

    #### UInt16。比较(UInt16)方法

    此方法用于将当前实例与指定的 16 位无符号整数进行比较，并返回一个整数，该整数显示当前实例的值是小于、等于还是大于指定的 16 位无符号整数的值。

    **语法:**

    ```cs
    public int CompareTo (ushort value);
    ```

    这里，需要一个无符号整数来进行比较。

    **返回值:**返回一个 32 位有符号数，表示当前实例和*值*参数的相对值，如下所示:

    *   **小于零:**如果当前实例<值
    *   **如果当前实例=值，则为零:**
    *   **大于零:**如果当前实例>值

    以下程序说明了 *UInt16 的使用。*比较法

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // UInt16.CompareTo(UInt16) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {

            // Declaring and initializing value1
            ushort value1 = 7;

            // Declaring and initializing value2
            ushort value2 = 98;

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
    7 is less than 98

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // UInt16.CompareTo(UInt16) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            // calling get() method
            get(54, 77);
            get(70, 95);
            get(10, 24);
            get(45, 45);
        }

        // defining get() method
        public static void get(ushort value1,
                               ushort value2)
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
    54 is less than 77
    70 is less than 95
    10 is less than 24
    45 is equal to 45

    ```

    #### UInt16。比较对象方法

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

    **异常:**如果*值*不是 *UInt16* ，则抛出*参数异常*。

    以下程序说明了 *UInt16 的使用。比较(对象)*方法

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // UInt16.CompareTo(object) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value1
                ushort value1 = 10;

                // Declaring and initializing value2
                object value2 = (ushort)56;

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
                           " or an instance of UInt16");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    10 is less than 56

    ```

    **示例 2:** 适用于*参数异常*

    ```cs
    // C# program to demonstrate the
    // UInt16.CompareTo(Object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value1
                ushort value1 = 150;

                // Declaring and initializing value2
                object value2 = 1 / 4;

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
                           " or an instance of UInt16");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    value2 must be null or an instance of UInt16
    Exception Thrown: System.ArgumentException

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . uint 16 . compare to？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint16.compareto?view=netstandard-2.1)**