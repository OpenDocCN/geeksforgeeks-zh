# C# | Insert()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-insert-method/](https://www.geeksforgeeks.org/c-sharp-insert-method/)

在 C# 中， ***Insert()*** 方法是一个 String 方法。它用于返回一个新字符串，其中指定的字符串被插入到当前字符串实例的指定索引位置。

**语法:**

```cs
public string Insert(int Indexvalue, string value)

```

**说明:**

*   **Index value:** is the index position of the current string, where the new value will be inserted. The type of this parameter is **system. Int32** 。
*   **Value:** The string value of the parameter type to be inserted is **system. String** .

**异常:**

*   **Parameter null exception:** If the string value is null.
*   **argumenterofrange exception:**唉呀 Indexvalue(索引值)阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云见阿云。

**注意:**这个方法总是返回一个新的字符串，该字符串被修改后的值被插入到指定的位置。Insert()方法的返回值类型是**系统。弦**。如果 Indexvalue 等于当前实例的长度，则该值将附加到此实例的末尾。

**例:**

```cs
Input : str  = "GeeksForGeeks"
        str.Insert(5, "GFG");
Output: GeeksGFGForGeeks

Input : str  = "GeeksForGeeks"
        str.Insert(8, " ");
Output: GeeksFor Geeks

```

下面是说明 Insert()方法的程序:

*   **Program 1:**

    ```cs
    // C# program to demonstrate the 
    // Insert method
    using System;
    class Geeks {

        // Main Method
        public static void Main()
        {

            // string
            String str = "GeeksForGeeks";

            Console.WriteLine("Current string: " + str);

            // insert GFG at index 5 where string is append
            Console.WriteLine("New string: " + str.Insert(5, "GFG"));
        }
    }
    ```

    **Output:**

    ```cs
    Current string: GeeksForGeeks
    New string: GeeksGFGForGeeks

    ```

*   **Program 2:**

    ```cs
    // C# program to demonstrate the 
    // Insert method
    using System;
    class Geeks {

        // Main Method 
        public static void Main()
        {

            // string
            String str = "GeeksForGeeks";

            Console.WriteLine("Current string: " + str);

            // insert space at index 8 where string is append
            Console.WriteLine("New string: " + str.Insert(8, " "));
        }
    }
    ```

    **Output:**

    ```cs
    Current string: GeeksForGeeks
    New string: GeeksFor Geeks

    ```

*   **Program 3:**

    ```cs
    // C# program to demonstrate the 
    // Insert method
    using System;
    class Geeks {

        // Main Method
        public static void Main()
        {
            Console.WriteLine("Hey Started".Insert(3, " ProGeek2.0"));
        }
    }
    ```

    **Output:**

    ```cs
    Hey ProGeek2.0 Started

    ```

**参考:**[https://msdn . Microsoft . com/en-us/library/system . string . insert](https://msdn.microsoft.com/en-us/library/system.string.insert(v=vs.110).aspx)