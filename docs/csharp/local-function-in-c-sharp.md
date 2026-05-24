# c# 中的局部函数

> 原文:[https://www.geeksforgeeks.org/local-function-in-c-sharp/](https://www.geeksforgeeks.org/local-function-in-c-sharp/)

在 **C# 7.0** 中引入了本地功能特性。它允许您在已经定义的方法体内声明一个方法。或者换句话说，我们可以说局部函数是一个函数的私有函数，它的作用域仅限于创建它的那个函数。局部函数的类型与定义它的函数的类型相似。您只能从它们的容器成员中调用本地函数。

**要点:**

*   局部函数在方法、构造函数、属性访问器、事件访问器、匿名方法、lambda 表达式、终结器和其他局部函数中声明。
*   不能在表达式主体成员中声明局部函数。
*   局部函数使您的程序更可读，也使您免于错误地调用方法，因为您不能直接调用局部函数。
*   在本地功能中，您可以使用*异步*和*不安全*修改器。
*   局部函数可以访问容器方法内部定义的局部变量，包括方法参数。
*   不允许在本地函数定义中使用任何成员访问修饰符，包括 private 关键字，因为默认情况下它们是私有的，并且不允许将其公开。
*   也不允许在局部函数中使用 static 关键字。
*   也不允许将属性应用于局部函数、其参数或其参数类型。
*   允许多个本地功能。
*   局部函数不允许重载。

**例 1:**

```cs
// C# program to illustrate local function
using System;

public class Program {

    // Main method
    public static void Main()
    {
        // Local Function
        void AddValue(int a, int b)
        {
            Console.WriteLine("Value of a is: " + a);
            Console.WriteLine("Value of b is: " + b);
            Console.WriteLine("Sum of a and b is: {0}", a + b);
            Console.WriteLine();
        }

        // Calling Local function
        AddValue(20, 40);
        AddValue(40, 60);
    }
}
```

**输出:**

```cs
Value of a is: 20
Value of b is: 40
Sum of a and b is: 60

Value of a is: 40
Value of b is: 60
Sum of a and b is: 100

```

**例 2:**

```cs
// C# program to illustrate local function 
// accessing the variable of the function 
// in which they present
using System;

public class Program {

    // Main method
    public static void Main()
    {
        // Variables of main method
        int x = 40;
        int y = 60;

        // Local Function
        void AddValue(int a, int b)
        {
            Console.WriteLine("Value of a is: " + a);
            Console.WriteLine("Value of b is: " + b);
            Console.WriteLine("Value of x is: " + x);
            Console.WriteLine("Value of y is: " + y);
            Console.WriteLine("Sum: {0}", a + b + x + y);
            Console.WriteLine();
        }

        // Calling Local function
        AddValue(50, 80);
        AddValue(79, 70);
    }
}
```

**输出:**

```cs
Value of a is: 50
Value of b is: 80
Value of x is: 40
Value of y is: 60
Sum: 230

Value of a is: 79
Value of b is: 70
Value of x is: 40
Value of y is: 60
Sum: 249

```

**局部功能优势:**

*   You are allowed to create local generic functions.

    **示例:**

    ```cs
    // C# program to illustrate how to
    // create local generic function
    using System;

    public class Program {

        // Main method
        public static void Main()
        {

            // Local Generic Function
            void MyMethod<MyValue>(MyValue value)
            {
                Console.WriteLine("Value is: " + value);
            }

            // Calling local generic function
            MyMethod<int>(123);
            MyMethod<string>("GeeksforGeeks");
            MyMethod<char>('G');
            MyMethod<double>(45453.5656);
        }
    }
    ```

    **输出:**

    ```cs
    Value is: 123
    Value is: GeeksforGeeks
    Value is: G
    Value is: 45453.5656

    ```

*   You are allowed to pass out/ref parameters in local functions.

    **示例:**

    ```cs
    // C# program to illustrate how can we
    // out prarameter in local function
    using System;

    public class Program {

        // Main method
        public static void Main()
        {

            // Local Function with out parameter
            void MyMethod(string str, out string s)
            {
                s = str + "for"
                    + "Geeks";
            }
            string a = null;

            // Calling Local function
            MyMethod("Geeks", out a);
            Console.WriteLine(a);
        }
    }
    ```

    **输出:**

    ```cs
    GeeksforGeeks
    ```

*   You are allowed to use params in local functions.

    **示例:**

    ```cs
    // C# program to illustrate how can we
    // pass params in local function
    using System;

    public class Program {

        // Main method
        public static void Main()
        {

            // Local Function
            // Using params
            void MyMethod(params string[] data)
            {
                for (int x = 0; x < data.Length; x++) 
                {
                    Console.WriteLine(data[x]);
                }
            }
            // Calling Local function
            MyMethod("Geeks", "gfg", "GeeksforGeeks", "123geeks");
        }
    }
    ```

    **输出:**

    ```cs
    Geeks
    gfg
    GeeksforGeeks
    123geeks
    ```