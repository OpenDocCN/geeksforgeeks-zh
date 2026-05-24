# Int64。C# 中的方法与示例的比较

> 原文:[https://www . geeksforgeeks . org/int 64-compare to-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int64-compareto-method-in-c-sharp-with-examples/)

**Int64。CompareTo 方法**用于将当前实例与指定的对象或 Int64 进行比较，并返回它们相对值的符号。此方法的重载列表中有 2 种方法，如下所示:

*   **比较(Int64)方法***   **CompareTo(Object) Method

    #### Int64。比较(Int64)方法

    此方法用于将当前实例与指定的 64 位有符号整数进行比较，并返回它们的相对值的符号。

    **语法:**

    ```cs
    public int CompareTo (long value);
    ```

    这里，需要整数来比较。

    **返回值:**返回一个 32 位有符号数，表示当前实例和*值*参数的相对值，如下所示:

    *   **小于零:**如果当前实例<值
    *   **如果当前实例=值，则为零:**
    *   **大于零:**如果当前实例>值

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Int64.CompareTo(Int64) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {

            // Declaring and initializing value1
            long value1 = 10;

            // Declaring and initializing value2
            long value2 = 20;

            // compare both Int64 value
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
    // Int64.CompareTo(Int64) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            // calling get() method
            get(5, 7);
            get(3025, 3025);
            get(10, 20);
            get(7, -12);
        }

        // defining get() method
        public static void get(long value1,
                               long value2)
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
    3025 is equal to 3025
    10 is less than 20
    7 is greater than -12

    ```

    #### Int64。比较对象方法

    此方法用于将当前实例与指定对象进行比较，并返回其相对值的符号。

    **语法:**

    ```cs
    public int CompareTo (object value);
    ```

    这里，它需要一个对象进行比较，或者为 null。

    **返回值:**返回一个 32 位有符号数，表示当前实例和*值*参数的相对值，如下所示:

    *   **小于零:**如果当前实例<值
    *   **零:**如果当前实例=值
    *   **大于零:**如果当前实例>值**或**值为空。

    **异常:**如果值不是 Int64，则抛出*参数异常*。

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Int64.CompareTo(object) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value1
                long value1 = 10;

                // Declaring and initializing value2
                object value2 = (long)5689412587;

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
                Console.WriteLine("value2 must be Int64");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    10 is less than 5689412587

    ```

    **示例 2:** 适用于*参数异常*

    ```cs
    // C# program to demonstrate the
    // Int64.CompareTo(object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value1
                long value1 = 10;

                // Declaring and initializing value2
                object value2 = 1/3;

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
                Console.WriteLine("value2 must be Int64");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    value2 must be Int64
    Exception Thrown: System.ArgumentException

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . int 64 . compare to？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int64.compareto?view=netframework-4.7.2)**