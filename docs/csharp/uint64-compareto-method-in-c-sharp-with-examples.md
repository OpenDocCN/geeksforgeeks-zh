# UInt64。将 C# 中的()方法与示例进行比较

> 原文:[https://www . geeksforgeeks . org/uint 64-compare to-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint64-compareto-method-in-c-sharp-with-examples/)

**UInt64。比较方法**用于将当前实例与指定的对象或另一个 UInt64 实例进行比较。它返回一个整数，该整数显示当前实例的值是小于、等于还是大于指定对象或其他 UInt64 实例的值。此方法的重载列表中有 2 种方法，如下所示:

*   **比较(UInt64)方法***   **CompareTo(Object) Method

    #### UInt64。比较(UInt64)方法

    此方法用于将当前实例与指定的 64 位无符号长整数进行比较，并返回一个整数，该整数显示当前实例的值是小于、等于还是大于指定的 64 位无符号长整数的值。

    **语法:**

    ```cs
    public int CompareTo (ulong value);
    ```

    这里，需要一个无符号长值来进行比较。

    **返回值:**返回一个 32 位有符号数，表示当前实例和*值*参数的相对值，如下所示:

    *   **小于零:**如果当前实例<值
    *   **如果当前实例=值，则为零:**
    *   **大于零:**如果当前实例>值

    以下程序说明了 *UInt64 的使用。比较(UInt64)* 方法:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // UInt64.CompareTo(UInt64) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {

            // Declaring and initializing value1
            ulong value1 = 312312131231;

            // Declaring and initializing value2
            ulong value2 = 523564123;

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
    312312131231 is greater than 523564123

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // UInt64.CompareTo(UInt64) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            // calling get() method
            get(34432425, 708343);
            get(3780, 8920);
            get(8543453910, 85345340920);
            get(7006789, 7006789);
        }

        // defining get() method
        public static void get(ulong value1,
                               ulong value2)
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
    34432425 is greater than 708343
    3780 is less than 8920
    8543453910 is less than 85345340920
    7006789 is equal to 7006789

    ```

    #### UInt64。比较对象方法

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

    **异常:**如果*值*不是 UInt64，则抛出*参数异常*。

    以下程序说明了 *UInt64 的使用。比较(对象)*方法

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // UInt64.CompareTo(Object) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value1
                ulong value1 = 2324313420;

                // Declaring and initializing value2
                object value2 = (ulong)687.876;

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
    2324313420 is greater than 687

    ```

    **示例 2:** 适用于*参数异常*

    ```cs
    // C# program to demonstrate the
    // UInt64.CompareTo(Object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value1
                ulong value1 = 104646549854;

                // Declaring and initializing value2
                object value2 = 1 / 6;

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
                           " or an instance of UInt64");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    value2 must be null or an instance of UInt64
    Exception Thrown: System.ArgumentException

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . uint 64 . compare to？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint64.compareto?view=netstandard-2.1)**