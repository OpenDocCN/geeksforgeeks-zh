# c# 中的注释

> 原文:[https://www.geeksforgeeks.org/comments-in-c-sharp/](https://www.geeksforgeeks.org/comments-in-c-sharp/)

注释用于解释代码，其使用方式类似于 Java、C 或 C++。编译器忽略注释条目，并且不执行它们。一般来说，编程语言包含两种类型的注释，但是在 C# 中，有 **3 种类型的注释**:

1.  **单行评论:**用来评论单行。这些注释可以写在单独的一行中，也可以与代码一起写在同一行中。但是为了更好地理解，请始终在单独的一行中使用注释。
    **语法:**

    ```cs
    // Single Line Comments
    ```

2.  **Multiline Comments :** It is used to comment more than one line. Generally this is used to comment out an entire block of code statements.
    **Syntax :**

    ```cs
    /* Multiline
    Comment */

    ```

    **示例:**

    ```cs
    // C# program to demonstrate the single 
    // line and multiline comments
    using System;

    namespace HelloGeeksApp {

    class HelloGeeks { 

        // Single Line Comment -- Function to print Message
        public static void Message(string message)
        {
            Console.WriteLine(message);
        }

        // Main function
        static void Main(string[] args)
        {

            /* Multiline Comment --
               Define a variable of
               string type and assign
               value to it*/
            string msg = "GeeksforGeeks";

            // Calling function
            Message(msg);
        }
    }
    }
    ```

    **Output:**

    ```cs
    GeeksforGeeks

    ```