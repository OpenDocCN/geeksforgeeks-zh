# C # 8.0 中的范围和指数

> 原文:[https://www . geesforgeks . org/range-and-indexs-in-c-sharp-8-0/](https://www.geeksforgeeks.org/range-and-indices-in-c-sharp-8-0/)

正如我们已经知道的[范围](https://www.geeksforgeeks.org/range-structure-in-c-sharp-8-0/)和[指数](https://www.geeksforgeeks.org/index-struct-in-c-sharp-8-0/)。我们在程序中多次使用它们，它们提供了一个简短的语法来表示或访问给定序列或集合中的单个或一系列元素。在本文中，我们将了解 C# 8.0 中的范围和索引中新增了什么。在 C# 8.0 中，范围和索引中添加了以下新内容:

**1。两种新类型**:

*   *系统。范围*:表示给定序列或集合的子范围。
*   *系统。索引*:表示给定序列或集合的索引。

**2。两个新操作员**:

*   **^ Operator:** It is known as the index from the end operator. It returns an index that is relative to the end of the sequence or collection. It is the most compact and easiest way to find the end elements compare to earlier methods.

    ```cs
    // Old Method
    var lastval = myarr[myarr.Length-1]

    // New Method
    var lastval = myarr[^1]

    ```

    **示例:**

    ```cs
    // C# program to illustrate the use 
    // of the index from end operator(^)
    using System;

    namespace example {

    class GFG {

        // Main Method
        static void Main(string[] args)
        {
            // Creating and initializing an array
            int[] myarr = new int[] {34, 56, 77, 88, 90, 45};

            // Simple getting the index value
            Console.WriteLine("Values of the specified indexes:");
            Console.WriteLine(myarr[0]);
            Console.WriteLine(myarr[1]);
            Console.WriteLine(myarr[2]);
            Console.WriteLine(myarr[3]);
            Console.WriteLine(myarr[4]);
            Console.WriteLine(myarr[5]);

            // Now we use index from end(^) 
            // operator with the given index
            // This will return the end value
            // which is related to the specified
            // index
            Console.WriteLine("The end values of the specified indexes:");
            Console.WriteLine(myarr[^1]);
            Console.WriteLine(myarr[^2]);
            Console.WriteLine(myarr[^3]);
            Console.WriteLine(myarr[^4]);
            Console.WriteLine(myarr[^5]);
            Console.WriteLine(myarr[^6]);
        }
    }
    }
    ```

    **输出:**

    ```cs
    Values of the specified indexes:
    34
    56
    77
    88
    90
    45
    The end values of the specified indexes:
    45
    90
    88
    77
    56
    34

    ```

    **解释:**在上面的例子中，我们有一个名为*myar*的 int 类型数组。在这里，我们首先简单地获取指定索引的值，即:

    ```cs
    34, 56, 77, 88, 90, 45
    Index : Value
     [0]  : 34
     [1]  : 56
     [2]  : 77
     [3]  : 88
     [4]  : 90
     [5]  : 45

    ```

    现在我们在^算子的帮助下找到指定索引的最后一个值，即:

    ```cs
    Index : Value
     [^1]  : 45
     [^2]  : 90
     [^3]  : 88
     [^4]  : 77
     [^5]  : 56
     [^6]  : 34

    ```

    **要点:**

    *   这个操作符的工作类似于 myar[arr。长度]。
    *   You are not allowed to use myarr[^0] if you use this, then this will throw an error because the end index starts from ^1, not from ^0 as shown in the below example:

        **示例:**

        ```cs
        // C# program to illustrate the use 
        // of the index from end operator(^)
        using System;

        namespace example {

        class GFG {

            // Main Method
            static void Main(string[] args)
            {
                // Creating and initializing an array
                int[] myarr = new int[] {34, 56,
                                77, 88, 90, 45};

                // Simply getting the index value
                Console.WriteLine("Values of the specified index:");
                Console.WriteLine(myarr[0]);

                // Now we use index from end(^)
                // operator with the given index
                // This will return the end value
                // which is related to the specified
                // index
                Console.WriteLine("The end values of the specified index:");
                Console.WriteLine(myarr[^0]);
            }
        }
        }
        ```

        **输出:**

        > 指定索引的值:
        > 34
        > 指定索引的结束值:
        > 未处理的异常。系统。IndexOutOfRangeException:索引超出了数组的界限。
        > 举例。/user/anki/Projects/example/program . cs 中的 Program.Main(String[] args):第 22 行

    *   You are allowed to use the index as a variable and this variable place in between brackets[]. As shown in the below example:

        **示例:**

        ```cs
        // C# program to illustrate how
        // to declare a index as a variable
        using System;

        namespace example {

        class GFG {

            // Main Method
            static void Main(string[] args)
            {

                // Creating and initializing an array
                int[] number = new int[] {1, 2, 3, 4,
                                      5, 6, 7, 8, 9};

                // Declare an index
                // as a variable
                Index i = ^6;
                var val = number[i];

                // Displaying number
                Console.WriteLine("Number: " + val);
            }
        }
        }
        ```

        **输出:**

        ```cs
        Number: 4
        ```

*   **.. Operator:** It is known as the range operator. And it specifies the start and end as its operands of the given range. It is the most compact and easiest way to find the range of the elements from the specified sequence or collection in comparison to earlier methods.

    ```cs
    // Old Method
    var arr = myemp.GetRange(1, 5);

    // New Method
    var arr = myemp[2..3]

    ```

    **示例:**

    ```cs
    // C# program to illustrate the 
    // use of the range operator(..)
    using System;

    namespace example {

    class GFG {

        // Main Method
        static void Main(string[] args)
        {
            // Creating and initializing an array
            string[] myemp = new string[] {"Anu", "Priya", "Rohit", 
                        "Amit", "Shreya", "Rinu", "Sumit", "Zoya"};

            Console.Write("Name of the employees in project A: ");
            var P_A = myemp[0..3];
            foreach(var emp1 in P_A)
                Console.Write({content}quot; [{emp1}]");

            Console.Write("\nName of the employees in project B: ");
            var P_B = myemp[3..5];
            foreach(var emp2 in P_B)
                Console.Write({content}quot; [{emp2}]");

            Console.Write("\nName of the employees in project C: ");
                var P_C = myemp[1..^2];
                foreach (var emp3 in P_C)
                    Console.Write({content}quot; [{emp3}]");

            Console.Write("\nName of the employees in project D: ");
            var P_D = myemp[..];
            foreach(var emp4 in P_D)
                Console.Write({content}quot; [{emp4}]");

            Console.Write("\nName of the employees in project E: ");
            var P_E = myemp[..2];
            foreach(var emp5 in P_E)
                Console.Write({content}quot; [{emp5}]");

            Console.Write("\nName of the employees in project F: ");
            var P_F = myemp[6..];
            foreach(var emp6 in P_F)
                Console.Write({content}quot; [{emp6}]");

            Console.Write("\nName of the employees in project G: ");
            var P_G = myemp[^3.. ^ 1];
            foreach(var emp7 in P_G)
                Console.Write({content}quot; [{emp7}]");
        }
    }
    }
    ```

    **输出:**

    ```cs
    Name of the employees in project A:  [Anu] [Priya] [Rohit]
    Name of the employees in project B:  [Amit] [Shreya]
    Name of the employees in project C:  [Priya] [Rohit] [Amit] [Shreya] [Rinu]
    Name of the employees in project D:  [Anu] [Priya] [Rohit] [Amit] [Shreya] [Rinu] [Sumit] [Zoya]
    Name of the employees in project E:  [Anu] [Priya]
    Name of the employees in project F:  [Sumit] [Zoya]
    Name of the employees in project G:  [Rinu] [Sumit]

    ```

    **要点:**

    *   当您使用 range 运算符创建一个范围时，它不会添加最后一个元素。例如，我们有一个数组{1，2，3，4，5，6 }，现在我们要打印范围[1..3]，那么它将打印 2、3。它不打印 2、3、4。
    *   在范围中，如果一个范围包含像范围[开始，结束]这样的开始和结束索引，那么这种类型的范围被称为有界范围。
    *   在范围中，如果一个范围只包含开始、结束索引或者不包含开始和结束索引，如范围[开始..]，或范围[..结束]或范围[..]，那么这种类型的范围被称为无界范围。
    *   You are allowed to use range as a variable and this variable place in between brackets[]. As shown in the below example:

        **示例:**

        ```cs
        // C# program to illustrate how to
        // declare a range as a variable
        using System;

        namespace example {

        class GFG {

            // Main Method
            static void Main(string[] args)
            {

                // Creating and initializing an array
                int[] number = new int[] {1, 2, 3, 4,
                                      5, 6, 7, 8, 9};

                Console.Write("Number: ");

                // Declaring a range as a variable
                Range num = 1..3;
                int[] val = number[num];

                // Displaying number
                foreach(var n in val)
                    Console.Write({content}quot; [{n}]");
            }
        }
        }
        ```

        **输出:**

        ```cs
        Number:  [2] [3]

        ```