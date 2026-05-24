# Int32。C# 中的 Equals 方法及示例

> 原文:[https://www . geesforgeks . org/int 32-equals-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int32-equals-method-in-c-sharp-with-examples/)

**Int32。Equals()方法**用于获取一个值，该值指示当前实例是否等于指定对象或 Int32。此方法的重载列表中有两种方法，如下所示:

*   **等于(Int32)方法***   **Equals(Object) Method

    #### Int32。等于(Int32)

    此方法用于返回一个值，该值指示当前实例是否等于指定的 Int32 值。

    > **语法:**public bool Equals(int obj)；
    > 这里，需要一个 Int32 值来与这个实例进行比较。
    > 
    > **返回值:**如果*对象*与该实例具有相同的值，则该方法返回真，否则返回假。

    以下程序说明了 *Int32 的使用。Equals(Int32)* 方法:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Int32.Equals(Int32) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing value1
            int value1 = 4562;

            // Declaring and initializing value2
            int value2 = 2563;

            // using Equals(Int32) method
            bool status = value1.Equals(value2);

            // checking the status
            if (status)
                Console.WriteLine("{0} is equal to {1}",
                                        value1, value2);
            else
                Console.WriteLine("{0} is not equal to {1}",
                                            value1, value2);
        }
    }
    ```

    **Output:**

    ```cs
    4562 is not equal to 2563

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Int32.Equals(Int32) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {

            // calling get() method
            get(455, 578);
            get(445, 445);
            get(10, 20);
            get(Int32.MaxValue, Int32.MinValue);
        }

        // defining get() method
        public static void get(int value1, int value2)
        {

            // using Equals(Int32) method
            bool status = value1.Equals(value2);

            // checking the status
            if (status)
                Console.WriteLine("{0} is equal to {1}",
                                        value1, value2);
            else
                Console.WriteLine("{0} is not equal to {1}",
                                            value1, value2);
        }
    }
    ```

    **Output:**

    ```cs
    455 is not equal to 578
    445 is equal to 445
    10 is not equal to 20
    2147483647 is not equal to -2147483648

    ```

    #### Int32。等于(对象)方法

    此方法用于返回一个值，该值指示当前实例是否等于指定的对象。

    > **语法:**公共覆盖 bool Equals(对象 obj)；
    > 在这里，需要一个对象来与这个实例进行比较。
    > 
    > **返回值:**如果*对象*是 Int32 的实例，并且等于该实例的值，则该方法返回真，否则返回假。

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Int32.Equals(Object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing value1
            int value1 = 10;

            // Declaring and initializing value2
            object value2 = 1 / 45;

            // using Equals(object) method
            bool status = value1.Equals(value2);

            // checking the status
            if (status)
                Console.WriteLine("{0} is equal to {1}",
                                        value1, value2);
            else
                Console.WriteLine("{0} is not equal to {1}",
                                            value1, value2);
        }
    }
    ```

    **Output:**

    ```cs
    10 is not equal to 0

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Int32.Equals(Object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // calling get() method
            get(547, 585);
            get(555, 489);
            get(100, 100);
            get(745, 725);
        }

        // defining get() method
        public static void get(int value1, 
                            object value2)
        {

            // compare both Int32 value
            // using Equals(object) method
            bool status = value1.Equals(value2);

            // checking the status
            if (status)
                Console.WriteLine("{0} is equal to {1}",
                                        value1, value2);
            else
                Console.WriteLine("{0} is not equal to {1}",
                                            value1, value2);
        }
    }
    ```

    **Output:**

    ```cs
    547 is not equal to 585
    555 is not equal to 489
    100 is equal to 100
    745 is not equal to 725

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . int 32 . equals？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int32.equals?view=netframework-4.7.2)**