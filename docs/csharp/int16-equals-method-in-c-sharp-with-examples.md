# Int16。C# 中的 Equals 方法及示例

> 原文:[https://www . geesforgeks . org/int 16-equals-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/int16-equals-method-in-c-sharp-with-examples/)

**Int16。Equals()方法**用于获取一个值，该值指示当前实例是否等于指定对象或 Int16。此方法的重载列表中有 2 种方法，如下所示:

*   **等于(Int16)方法***   **Equals(Object) Method

    #### Int16。等于(Int16)

    此方法用于返回一个值，该值指示当前实例是否等于指定的 Int16 值。

    > **语法:** public bool Equals(短 obj)；
    > 这里，需要一个 Int16 值来与这个实例进行比较。
    > 
    > **返回值:**如果*对象*与该实例具有相同的值，则该方法返回*真*，否则返回*假*。

    以下程序说明了 *Int16 的使用。Equals(Int16)* 方法:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Int16.Equals(Int16) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing value1
            short value1 = 15;

            // Declaring and initializing value2
            short value2 = 17;

            // compare both Int16 value
            // using Equals(Int16) method
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
    15 is not equal to 17

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Int16.Equals(Int16) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {

            // calling get() method
            get(5, 5);
            get(5, 4);
            get(10, 20);
            get(7, 7);
        }

        // defining get() method
        public static void get(short value1,
                               short value2)
        {

            // Compare both Int16 value
            // using Equals(Int16) method
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
    5 is equal to 5
    5 is not equal to 4
    10 is not equal to 20
    7 is equal to 7

    ```

    #### Int16。等于(对象)方法

    此方法用于返回一个值，该值指示当前实例是否等于指定的对象。

    > **语法:**公共覆盖 bool Equals(对象 obj)；
    > 在这里，需要一个对象来与这个实例进行比较。
    > 
    > **返回值:**如果*对象*是 Int16 的一个实例，并且等于该实例的值，则该方法返回 *true* ，否则返回 false。

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Int16.Equals(Object) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing value1
            short value1 = 10;

            // Declaring and initializing value2
            // It will convert into Int16 implicitly 
            // by the compiler to check whether it is 
            // in the range of short data type i.e. 
            // Int16 or not
            object value2 = 37;

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
    10 is not equal to 37

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Int16.Equals(Object) Method
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {
            // calling get() method
            get(5, 5);
            get(5, 4);
            get(10, 20);
            get(7, 7);
        }

        // defining get() method
        // The second parameter will get converted to Int16  
        // implicitly by the compiler to check whether  
        // it is in the range of short data type i.e. 
        // Int16 or not
        public static void get(short value1,
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
    5 is not equal to 5
    5 is not equal to 4
    10 is not equal to 20
    7 is not equal to 7

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . int 16 . equals？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int16.equals?view=netframework-4.7.2)**