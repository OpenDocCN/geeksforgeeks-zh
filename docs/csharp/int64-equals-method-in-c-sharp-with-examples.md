# Int64。C# 中的 Equals 方法及示例

> 原文:[https://www . geesforgeks . org/int 64-equals-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int64-equals-method-in-c-sharp-with-examples/)

**Int64。Equals()方法**用于获取一个值，该值显示当前实例是否等于指定对象或 Int64。此方法的重载列表中有 2 种方法，如下所示:

*   **等于(Int64)方法***   **Equals(Object) Method

    #### Int64。等于(Int64)

    此方法用于返回一个值，该值指示当前实例是否等于指定的 Int64 值。

    > **语法:**public bool Equals(long obj)；
    > 这里，需要一个 Int64 值来与这个实例进行比较。
    > 
    > **返回值:**如果*对象*与该实例具有相同的值，则该方法返回真，否则返回假。

    以下程序说明了 *Int64 的使用。Equals(Int64)* 方法:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Int64.Equals(Int64) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing value1
            long value1 = 45643242;

            // Declaring and initializing value2
            long value2 = 2564233;

            // using Equals(Int64) method
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
    45643242 is not equal to 2564233

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Int64.Equals(Int64) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {

            // calling get() method
            get(44355, 578);
            get(423445, 423445);
            get(12560, 28960);
            get(778, 798);
        }

        // defining get() method
        public static void get(long value1,
                               long value2)
        {

            // using Equals(Int64) method
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
    44355 is not equal to 578
    423445 is equal to 423445
    12560 is not equal to 28960
    778 is not equal to 798

    ```

    #### Int64。等于(对象)方法

    此方法用于返回一个值，该值指示当前实例是否等于指定的对象。

    > **语法:**公共覆盖 bool Equals(对象 obj)；
    > 在这里，需要一个对象来与这个实例进行比较。
    > 
    > **返回值:**如果*对象*是 Int64 的实例，并且等于该实例的值，则该方法返回 *true* ，否则返回 false。

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Int64.Equals(Object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing value1
            long value1 = 1879650;

            // Declaring and initializing value2
            object value2 = 1/45;

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
    1879650 is not equal to 0

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Int64.Equals(Object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // calling get() method
            get(54547, 54585);
            get(555, 489);
            get(10450, 10450);
            get(745, 745);
        }

        // defining get() method
        public static void get(long value1,
                            object value2)
        {

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
    54547 is not equal to 54585
    555 is not equal to 489
    10450 is not equal to 10450
    745 is equal to 745

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . int 64 . equals？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int64.equals?view=netframework-4.7.2)**