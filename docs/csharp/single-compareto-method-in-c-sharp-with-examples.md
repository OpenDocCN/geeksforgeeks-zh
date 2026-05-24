# 单身。将 C# 中的()方法与示例进行比较

> 原文:[https://www . geeksforgeeks . org/single-compare to-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/single-compareto-method-in-c-sharp-with-examples/)

**单身。CompareTo()方法**用于将当前实例与指定对象或另一个 Single 实例进行比较，并返回一个整数，该整数显示当前实例的值是大于、等于还是小于指定对象或另一个 *Single* 实例的值。此方法的重载列表中有 2 种方法，如下所示:

*   **比较(单一)方法***   **CompareTo(Object) Method

    #### 单身。比较(单一)方法

    此方法用于将当前实例与指定的单精度浮点数进行比较，并返回一个整数，该整数指示此实例的值是小于、等于还是大于指定的单精度浮点数的值。

    **语法:**

    ```cs
    public int CompareTo (float value);
    ```

    这里，需要一个单精度浮点数进行比较。

    **返回值:**返回一个 32 位有符号数，表示当前实例和*值*参数的相对值，如下所示:

    *   **小于零:**如果当前实例<值或当前实例不是数字( *NaN* )且值是数字。
    *   **零:**如果当前实例=值或当前实例和*值*都不是数字( *NaN* )、 *PositiveInfinity* 或 *NegativeInfinity* 。
    *   **大于零:**如果当前实例>值或当前实例是一个数字并且值不是一个数字( *NaN* )。

    以下程序说明了 *Single 的使用。比较(单一)*方法:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Single.CompareTo(Single) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {

            // Declaring and initializing value1
            float value1 = 10.5f;

            // Declaring and initializing value2
            float value2 = 20.6f;

            // compare both the values
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
    10.5 is less than 20.6

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Single.CompareTo(Single) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            // calling get() method
            get(5.4f, 7.5f);
            get(30.4f, 20.3f);
            get(10.4f, 10.4f);
            get(7.2f, -12.3f);
        }

        // defining get() method
        public static void get(float value1,
                               float value2)
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
    5.4 is less than 7.5
    30.4 is greater than 20.3
    10.4 is equal to 10.4
    7.2 is greater than -12.3

    ```

    #### 单身。比较对象方法

    此方法用于将当前实例与指定对象进行比较，并返回一个整数，该整数显示当前实例的值是小于、等于还是大于指定对象的值。

    **语法:**

    ```cs
    public int CompareTo (object value);
    ```

    这里，它将对象与这个实例进行比较，或者为 null。

    **返回值:**返回一个 32 位有符号数，表示当前实例和*值*参数的相对值，如下所示:

    *   **小于零:**如果当前实例<值或当前实例不是数字( *NaN* )且值是数字。
    *   **零:**如果当前实例=值或当前实例和*值*都不是数字( *NaN* )、 *PositiveInfinity* 或 *NegativeInfinity* 。
    *   **大于零:**如果当前实例>值或当前实例是一个数字并且值不是一个数字( *NaN* )。

    **异常:**如果值不是*单*，则抛出*参数异常*。

    以下程序说明了 *Single 的使用。比较(对象)*方法

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Single.CompareTo(Object) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value1
                float value1 = 10.4f;

                // Declaring and initializing value2
                object value2 = 10.5f;

                // compare both the value
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
                Console.WriteLine("value2 must be Single");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    10.4 is less than 10.5

    ```

    **示例 2:** 适用于*参数异常*

    ```cs
    // C# program to demonstrate the
    // Single.CompareTo(object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            try {

                // Declaring and initializing value1
                float value1 = 10;

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
                Console.WriteLine("value2 must be Single");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    value2 must be Single
    Exception Thrown: System.ArgumentException

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . single . compare to？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.single.compareto?view=netstandard-2.1)**