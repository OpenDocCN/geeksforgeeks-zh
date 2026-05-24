# Int16。C# 中的 CompareTo()方法

> 原文:[https://www . geesforgeks . org/int 16-compare to-method-in-c-sharp/](https://www.geeksforgeeks.org/int16-compareto-method-in-c-sharp/)

**Int16。比较方法**用于将当前实例与指定对象或另一个 Int16 实例进行比较。它返回一个整数，该整数显示当前实例的值是小于、等于还是大于指定对象或其他 Int16 实例的值。此方法的重载列表中有 2 种方法，如下所示:

*   **比较(Int16)方法***   **CompareTo(Object) Method

    #### Int16。比较(Int16)方法

    此方法用于将当前实例与指定的 16 位有符号整数进行比较，并返回一个整数，该整数显示当前实例的值是小于、等于还是大于指定的 16 位有符号整数的值。

    **语法:**

    ```cs
    public int CompareTo (short value);
    ```

    这里，需要一个整数来比较。

    **返回值:**返回一个 32 位有符号数，表示当前实例和*值*参数的相对值，如下所示:

    *   **小于零:**如果当前实例<值
    *   **如果当前实例=值，则为零:**
    *   **大于零:**如果当前实例>值

    以下程序说明了 *Int16 的使用。比较(Int16)* 方法

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Int16.CompareTo(Double) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {

            // Declaring and initializing value1
            short value1 = 1;

            // Declaring and initializing value2
            short value2 = 5;

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
    1 is less than 5

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Int16.CompareTo(Double) Method
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
        public static void get(short value1,
                               short value2)
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

    #### Int16。比较对象方法

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

    **异常:**如果*值*不为空，则抛出*参数异常*。

    以下程序说明了 *Int16 的使用。比较(对象)*方法

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Int16.CompareTo(object) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value1
                short value1 = 10;

                // Declaring and initializing value2
                object value2 = (short)9.8765400;

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
                Console.WriteLine("value2 must be short");
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
    // Int16.CompareTo(object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value1
                short value1 = 10;

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

            catch (ArgumentException e) {
                Console.WriteLine("value2 must be short");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    value2 must be short
    Exception Thrown: System.ArgumentException

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . int 16 . compare to？视图=netcore-2.2](https://docs.microsoft.com/en-us/dotnet/api/system.int16.compareto?view=netcore-2.2)**