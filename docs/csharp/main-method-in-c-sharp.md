# c# 中的主要方法

> 原文:[https://www.geeksforgeeks.org/main-method-in-c-sharp/](https://www.geeksforgeeks.org/main-method-in-c-sharp/)

C# 应用程序有一个 ***入口点*** 叫做 Main Method。它是第一个在应用程序启动时被调用的方法，并且存在于每个 C# 可执行文件中。应用程序可以是控制台应用程序或窗口应用程序。C# 程序最常见的入口点是 **`static void Main()`** 或 **`static void Main(String []args)`** 。

#### Main()方法的不同声明

下面是 C# 程序中 Main 方法的有效声明:

1.  **With [command line arguments](https://www.geeksforgeeks.org/c-command-line-arguments/):** This can accept n number of array type parameters during the runtime.

    **示例:**

    ```cs
    using System;

    class GFG {

        // Main Method
        static public void Main(String[] args)
        {

            Console.WriteLine("Main Method");
        }
    }
    ```

    **输出:**

    ```cs
    Main Method
    ```

    **主要语法的含义:**

    > **static:** 表示没有对象也可以调用 Main Method。
    > **public:** 它是访问修饰符，这意味着编译器可以从任何地方执行它。
    > **虚空:**主法不回任何东西。
    > **Main():** 是 Main 方法的配置名称。
    > **字符串[]参数:**用于接受*零索引命令行参数*。args 是用户定义的名称。所以你可以用一个有效的标识符来改变它。[]必须在 args 之前，否则编译器会给出错误。

2.  **Without Command line arguments:** It is up to the user whether he wants to take command line arguments or not. If there is a need for command-line arguments then the user must specify the command line arguments in the Main method.

    **示例:**

    ```cs
    using System;

    class GFG {

        // Main Method
        static public void Main()
        {

            Console.WriteLine("Main Method");
        }
    }
    ```

    **输出:**

    ```cs
    Main Method
    ```

3.  **Applicable Access Modifiers:** public, private, protected, internal, protected internal access modifiers can be used with the Main() method. The **private protected** access modifier cannot be used with it.

    **示例:**

    ```cs
    using System;

    class GFG {

        // Main Method
        protected static void Main()
        {

            Console.WriteLine("Main Method");
        }
    }
    ```

    **输出:**

    ```cs
    Main Method
    ```

    **示例:**

    ```cs
    using System;

    class GFG {

        // Main Method
        private protected static void Main()
        {

            Console.WriteLine("Main Method");
        }
    }
    ```

    **编译器错误:**

    > 指定了多个保护修饰符

4.  **Without any access modifier:** The default access modifier is private for a Main() method.

    **示例:**

    ```cs
    using System;

    class GFG {

        // Main Method without any
        // access modifier
        static void Main()
        {

            Console.WriteLine("Main Method");
        }
    }
    ```

    **输出:**

    ```cs
    Main Method
    ```

5.  **Order of Modifiers:** The user can also swap positions of static and applicable modifiers in Main() method.

    **示例:**

    ```cs
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {

            Console.WriteLine("Main Method");
        }
    }
    ```

    **输出:**

    ```cs
    Main Method
    ```

    **示例:**

    ```cs
    using System;

    class GFG {

        // Main Method with swapping of modifiers
        static internal void Main()
        {

            Console.WriteLine("Main Method");
        }
    }
    ```

    **输出:**

    ```cs
    Main Method
    ```

6.  **Return Type:** The Main Method can also have integer return type. Returning an integer value from Main() method cause the program to obtain a status information. The value which is returned from Main() method is treated as the exit code for the process.

    **示例:**

    ```cs
    using System;

    class GFG {

        // Main Method with int return type
        static int Main()
        {

            Console.WriteLine("Main Method");

            // for successful execution of code
            return 0;
        }
    }
    ```

    **输出:**

    ```cs
    Main Method
    ```

    **示例:**

    ```cs
    using System;

    class GFG {

        // Main Method with int return type
        static int Main(String[] args)
        {

            Console.WriteLine("Main Method");

            // for successful execution of code
            return 0;
        }
    }
    ```

    **输出:**

    ```cs
    Main Method
    ```

**要点:**

*   Main()方法是 C# 程序的入口点，从这里开始执行。
*   Main()方法**必须是静态的**，因为是类级别的方法。要在没有任何类实例的情况下调用，它必须是静态的。非静态 Main()方法会产生编译时错误。
*   Main()方法**不能被**覆盖，因为它是静态方法。此外，静态方法不能是虚拟的或抽象的。
*   **Overloading of Main() method** is allowed. But in that case, only one Main() method is considered as one entry point to start the execution of the program.

    **示例:**Main()方法的有效重载

    ```cs
    // C# program to demonstrate the
    // Valid overloading of Main()
    // method
    using System;

    class GFG {

        // Main method
        // it can also be written as
        // static void Main(String []args)
        static void Main()
        {
            Console.WriteLine("Main Method");
        }

        // overloaded Main() Method
        static void Main(int n)
        {
            Console.WriteLine("Overloaded Main Method");
        }

        // overloaded Main() Method
        static void Main(int x, int y)
        {
            Console.WriteLine("Overloaded Main Method");
        }
    }
    ```

    **输出:**

    ```cs
    Main Method

    ```

    **警告:**

    > prog.cs(17，14):警告 CS0028: `GFG.Main(int)'有错误的签名作为入口点
    > prog.cs(23，14):警告 CS0028: `GFG.Main(int，int)'有错误的签名作为入口点

    **示例:**Main()方法无效重载

    ```cs
    // C# program to demonstrate the
    // Invalid overloading of Main()
    // method
    using System;

    class GFG {

        // Main method
        // it can also be written as
        // static void Main()
        static void Main(String[] args)
        {
            Console.WriteLine("Main Method");
        }

        // overloaded Main() Method
        static void Main()
        {
            Console.WriteLine("Overloaded Main Method");
        }
    }
    ```

    **编译错误:**

    > prog.cs(11，14):错误 CS0017:程序` 5c 56 b 8183078 e 496102 B7 f 2662 F8 b 84e . exe '定义了多个入口点:` gfg . main(string[])'
    > Prog . cs(17，14):错误 CS0017:程序` 5c 56 b 8183078 e 496102 B7 f 2662 F8 b 84e . exe '定义了多个入口点

*   命令行参数的允许类型在 Main()方法的参数中只有**字符串数组**。
*   Main()方法允许的**返回类型**为 **void、int、Task(来自 C# 7.1)和 Task < T >(来自 C# 7.1)** 。
*   如果 Main()方法的返回类型为 Task 或 Task < T >，则 Main()方法的声明可能包含**异步修饰符**。
*   C# 中的库和服务不需要 Main()方法作为入口点。
*   如果不止一个 C# 类包含 main()方法，那么用户必须用 **/main** 选项编译程序，以指定哪个 Main()方法将是入口点。