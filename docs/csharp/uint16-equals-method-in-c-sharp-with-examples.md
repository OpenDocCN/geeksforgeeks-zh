# UInt16。C# 中的 Equals 方法及示例

> 原文:[https://www . geesforgeks . org/uint 16-equals-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uint16-equals-method-in-c-sharp-with-examples/)

**UInt16。Equals 方法**用于获取一个值，该值指示当前实例是否等于指定的对象或 16 位无符号整数。此方法的重载列表中有 2 种方法，如下所示:

*   **等于(UInt16)方法***   **Equals(Object) Method

    #### UInt16。等于(UInt16)方法

    此方法用于返回一个值，该值指示当前实例是否等于指定的 16 位无符号整数值。

    > **语法:**public bool Equals(ushort obj)；
    > 这里，需要一个 16 位无符号整数值来与当前实例进行比较。
    > 
    > **返回值:**如果*对象*与该实例具有相同的值，则该方法返回 *true* ，否则返回 false。

    以下程序说明了 *UInt16 的使用。等于(UInt16)* 方法:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // UInt16.Equals(UInt16) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing value1
            ushort value1 = 52;

            // Declaring and initializing value2
            ushort value2 = 78;

            // using Equals(UInt16) method
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
    52 is not equal to 78

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // UInt16.Equals(UInt16) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {

            // calling get() method
            get(98, 18);
            get(65, 65);
            get(100, 40);
            get(UInt16.MaxValue, UInt16.MinValue);
        }

        // defining get() method
        public static void get(ushort value1,
                               ushort value2)
        {

            // using Equals(UInt16) method
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
    98 is not equal to 18
    65 is equal to 65
    100 is not equal to 40
    65535 is not equal to 0

    ```

    #### UInt16。等于(对象)方法

    此方法用于返回一个值，该值指示当前实例是否等于指定的对象。

    > **语法:**公共覆盖 bool Equals(对象 obj)；
    > 这里，需要一个对象与当前实例进行比较。
    > 
    > **返回值:**如果*对象*是 UInt16 的实例，并且等于该实例的值，则该方法返回 *true* ，否则返回 false。

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // UInt16.Equals(Object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing value1
            ushort value1 = 17;

            // Declaring and initializing value2
            object value2 = 1 / 7;

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
    17 is not equal to 0

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // UInt16.Equals(Object) Method
    using System;
    using System.Globalization;

    class GFG {

        // Main Method
        public static void Main()
        {
            // calling get() method
            get(12, 75);
            get(14, 114);
            get(77, 77);
            get(54, 76);
        }

        // defining get() method
        public static void get(ushort value1,
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
    12 is not equal to 75
    14 is not equal to 114
    77 is not equal to 77
    54 is not equal to 76

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . uint 16 . equals？视图=网络标准-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.uint16.equals?view=netstandard-2.1)**