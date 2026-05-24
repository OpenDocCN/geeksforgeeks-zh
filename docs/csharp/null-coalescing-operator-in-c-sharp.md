# c# 中的空合并运算符

> 原文:[https://www . geeksforgeeks . org/null-聚结-运算符 in-c-sharp/](https://www.geeksforgeeks.org/null-coalescing-operator-in-c-sharp/)

在 C# 中**？？运算符**被称为空值合并运算符。如果左侧操作数不为空，它将返回其值。如果它为空，那么它将计算右边的操作数并返回其结果。或者，如果左侧操作数的计算结果为非空，则不会计算其右侧操作数。

**语法:**

```cs
p ?? q
```

这里，p 是左操作数，q 是右操作数？？操作员。p 的值可以是可空类型，但 q 的值必须是不可空类型。如果 p 的值为空，则返回 q 的值，否则返回 p 的值。

**要点:**

*   那个？？运算符用于检查空值，您还可以为值为空(或可空类型)的变量分配默认值。
*   你不准霸王？？操作员。
*   它是右联想的。
*   在吗？？运算符，可以使用 throw 表达式作为？？运算符，这使得您的代码更加简洁。
*   You are allowed to use ?? operator with value types and reference types.

    **示例:**

    ```cs
    // C# program to illustrate how to use 
    // ?? operator with value types and
    // reference types
    using System;

    namespace example {

    class Program {
        static void Main(string[] args)
        {

            // Reference types
            string item_1 = null;
            string item_2 = "GeeksforGeeks";
            string item_3 = "GFG";

            string item_4 = item_1 ?? item_2;
            item_3 = item_4 ?? item_2;

            Console.WriteLine("Value of item_4 is: {0} \n"+
                  "Value of item_3 is: {1}", item_4, item_3);

            // Value types
            int ? item_5 = null;

            Program obj = new Program();

            // Using ?? operator assigns
            // the value of a value type
            // and also you are allowed 
            // to use method with ?? operator
            int ? item_6 = item_5 ?? obj.Add(10, 30);
            Console.WriteLine("Value of item_6 is: {0}", item_6);
        }

        // Method
        public int Add(int a, int b)
        {
            int result = a + b;
            return result;
        }
    }
    }
    ```

    **输出:**

    ```cs
    Value of item_4 is: GeeksforGeeks 
    Value of item_3 is: GeeksforGeeks
    Value of item_6 is: 40

    ```

*   With the help of ?? operator you can prevent **InvalidOperationException**.

    **示例:**

    ```cs
    // C# program to illustrate how ?? 
    // operator prevent the 
    // InvalidOperationException
    using System;

    namespace example {

    class GFG {

        // Main Method
        static void Main(string[] args)
        {
            // Creating items of nullable types
            int ? item_1 = null;

             /*
             Here if you use this commented part,
             then this statement will give you an
             InvalidOperationException. So to 
             overcome this problem we use ?? operator 
             int? item_2 = item_1.Value;
             */

            // With the help of ?? operator we 
            // assign a default value to the item_2
            // And the value of item_1 is null.
            int ? item_2 = item_1 ?? 100;
            Console.WriteLine("Value of item_1 is: {0}", item_1);
            Console.WriteLine("Value of item_2 is: {0}", item_2);
        }
    }
    }
    ```

    **输出:**

    ```cs
    Value of item_1 is: 
    Value of item_2 is: 100

    ```

*   With the help of ?? operator you can remove many redundant “if-else” conditions and make your code compact and readable.

    **示例:**

    ```cs
    // C# program to illustrate how ?? 
    // operator replaces if-else statements
    using System;

    namespace example {

    class GFG {

        // Main Method
        static void Main(string[] args)
        {
            // Creating items of nullable types
            int ? item_1 = null;

            int ? item_2;

            if (item_1.HasValue) {
                item_2 = item_1;
            }
            else {
                item_2 = 200;
            }
            Console.WriteLine("Value of item_1 is: {0}", item_1);
            Console.WriteLine("Value of item_2 is: {0}", item_2);
        }
    }
    }
    ```

    **输出:**

    ```cs
    Value of item_1 is: 
    Value of item_2 is: 200

    ```

    ```cs
    // C# program to illustrate how ??
    // operator replaces if-else statements
    using System;

    namespace example {

    class GFG {

        // Main Method
        static void Main(string[] args)
        {
            // Creating items of nullable types
            int ? item_1 = null;

            // Using ?? operator
            int ? item_2 = item_1 ?? 200;
            Console.WriteLine("Value of item_1 is: {0}", item_1);
            Console.WriteLine("Value of item_2 is: {0}", item_2);
        }
    }
    }
    ```

    **输出:**

    ```cs
    Value of item_1 is: 
    Value of item_2 is: 200

    ```

*   ?? operator can be nested. It will make your code more readable and also reduce multiple if-else conditions.

    **示例:**

    ```cs
    // C# program to illustrate how 
    // we use nested ?? operator
    using System;

    namespace example {

    class GFG {

        // Main Method
        static void Main(string[] args)
        {
            // Creating items of nullable types
            int ? item_1 = null;
            int ? item_2 = null;
            int ? item_3 = 500;

            // Nested ?? operator
            int ? item_4 = item_1 ?? item_2 ?? item_3;

            Console.WriteLine("Value of item_4 is: {0} ", item_4);
        }
    }
    }
    ```

    **输出:**

    ```cs
    Value of item_4 is: 500 
    ```