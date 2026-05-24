# C# | Char。GetNumericValue()方法

> 原文:[https://www . geesforgeks . org/c-sharp-char-getnumericvalue-method/](https://www.geeksforgeeks.org/c-sharp-char-getnumericvalue-method/)

在 C# 中， ***Char。*** 是一个*系统。Char* 结构方法，用于将一个数字 Unicode 字符转换为双精度浮点数。数值必须属于 *UnicodeCategory* ，即*十进制数字*、*字母数字*或*其他数字*。通过向该方法传递不同类型和数量的参数，可以重载该方法。

*   **夏尔。GetNumericValue(字符串，Int32)方法***   **Char.GetNumericValue(Char) Method

    #### 夏尔。GetNumericValue(字符串，Int32)方法

    此方法用于将指定字符串中指定位置的数字 Unicode 字符转换为双精度浮点数。字符串中的字符位置总是从零开始。

    **语法:**

    ```cs
    public static double GetNumericValue(String str, int index);
    ```

    **参数:**

    > **字符串:**是*系统类型的指定字符串。弦*。
    > 
    > **索引:**表示字符串 *str* 中的字符位置，该参数的类型为*系统。Int32* 。

    **返回类型:**如果字符由数字表示，则该方法在*字符串*中的*索引*位置返回一个数值，否则返回-1。该方法的返回类型为**系统。双**。

    **异常:**

    *   如果给定字符串 *str* 的值为空，则该方法将给出 *ArgumentNullException* 。
    *   如果*索引*小于零或大于*字符串*中的最后一个位置，则此方法将给出*argumentout of range exception*。

    **示例:**

    ```cs
    // C# program to illustrate the
    // Char.GetNumericValue(String, Int32) Method
    using System;

    class GeeksforGeeks {

        // Main method
        public static void Main()
        {

            // declaration of datatype
            double output;
            string str = "geeks213";

            // provide numeric value of position 4
            output = Char.GetNumericValue(str, 4);
            Console.WriteLine(output);

            // provide numeric value of position 7
            output = Char.GetNumericValue(str, 7);
            Console.WriteLine(output);
        }
    }
    ```

    **Output:**

    ```cs
    -1
    3

    ```

    #### 夏尔。获取数值(字符)方法

    此方法用于将指定的 Unicode 字符转换为双精度浮点数。

    **语法:**

    ```cs
    public static double GetNumericValue(Char ch);
    ```

    **参数:**

    > **ch** :是要转换为双精度浮点数的 Unicode 字符。

    **返回类型:**如果一个字符代表一个数字，那么这个方法返回 *ch* 的数值，否则返回-1.0。这种方法的返回类型是**系统。双**。

    **示例:**

    ```cs
    // C# program to illustrate the
    // Char.GetNumericValue(Char) Method
    using System;

    class GeeksforGeeks {

        // Main method
        public static void Main()
        {

            // using Char.GetNumericValue(char method)
            Console.WriteLine(Char.GetNumericValue('9'));
            Console.WriteLine(Char.GetNumericValue('z'));
        }
    }
    ```

    **Output:**

    ```cs
    9
    -1

    ```

    **参考:**[https://docs . Microsoft . com/en-us/dotnet/API/system . char . getnumericvalue？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.char.getnumericvalue?view=netframework-4.7.2)**