# C# | Char。ToString()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-char-tostring-method/](https://www.geeksforgeeks.org/c-sharp-char-tostring-method/)

在 C# 中， **Char。ToString()** 是一个*系统。Char* struct 方法，用于将此实例的值转换为其等效的字符串表示形式。这个方法可以通过传递不同类型的参数来重载。

*   **夏尔。ToString(表单提供商)方法***   **夏尔。字符串(字符)方法***   **Char.ToString() Method

    #### 夏尔。ToString(表单提供商)方法

    此方法用于通过使用指定的区域性特定格式信息，将当前实例的值转换为其等效的字符串表示形式。特定于区域性的格式是一种格式，它是将类、结构或枚举的实例值转换为字符串表示形式并将结果显示给用户的过程。

    **语法:**

    ```cs
    public string ToString(IFormatProvider provider);
    ```

    **参数:**

    > **提供者**:提供特定于区域性的格式信息的必选对象，保留。

    **返回类型:**返回参数*提供者*指定的当前实例值的字符串表示形式。这种方法的返回类型是*系统。弦*。

    **示例:**

    ```cs
    // C# program to illustrate the
    // Char.ToString(IFormatProvider) Method
    using System;

    class GeeksforGeeks{

        // Main method
        public static void Main() {

            // converting into string
            Console.WriteLine(Char.ToString('G')); 
        }
    }
    ```

    **Output:**

    ```cs
    G

    ```

    **注意:**这里参数*提供者*被忽略，因为它不参与这个操作。

    #### 夏尔。字符串(字符)方法

    此方法用于将指定的 Unicode 字符转换为字符串表示形式。

    **语法:**

    ```cs
    public static string ToString(Char ch);
    ```

    **参数:**

    > **ch** :是要转换的 Unicode 字符。

    **返回类型:**返回参数 *ch* 的字符串表示。这种方法的返回类型是**系统。弦**。

    **示例:**

    ```cs
    // C# program to illustrate the
    // Char.ToString(Char) Method
    using System;

    class GeeksforGeeks{

        // Main method
        public static void Main() {

            // using ToString(Char) method
            // for converting char into string
            Console.WriteLine(Char.ToString('A'));
        }
    }
    ```

    **Output:**

    ```cs
    A

    ```

    #### 夏尔。ToString()方法

    此方法用于将此实例的值转换为其等效的字符串表示形式。

    **语法:**

    ```cs
    public override string ToString();
    ```

    **返回类型:**返回该实例值的字符串表示形式。这种方法的返回类型是*系统。弦*。

    **示例:**

    ```cs
    // C# program to illustrate the
    // Char.ToString() Method
    using System;

    class GeeksforGeeks{

        // Main method
        public static void Main() {

            // declaration of data type
            char ch1 = 'P';
            string output;

            // convert into a string
            output = ch1.ToString();
            Console.WriteLine(output);

        }
    }
    ```

    **Output:**

    ```cs
    P

    ```

    **参考:**[https://docs . Microsoft . com/en-us/dotnet/API/system . char . tostring？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.char.tostring?view=netframework-4.7.2)**