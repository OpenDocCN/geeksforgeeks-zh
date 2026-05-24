# C# |颠倒整个列表或指定范围内元素的顺序

> 原文:[https://www . geesforgeks . org/c-sharp-颠倒整个列表或指定范围内元素的顺序/](https://www.geeksforgeeks.org/c-sharp-reverse-the-order-of-the-elements-in-the-entire-list-or-in-the-specified-range/)

**列表< T >。反转方法**用于反转列表<中元素的顺序>或其一部分。列表< T >的过载列表中有两种方法。反向方法如下:

*   **反向()***   **Reverse(Int32, Int32)

    #### 反向()方法

    此方法用于颠倒整个列表<t>中元素的顺序。</t>

    **语法:**

    ```cs
    public void Reverse ();
    ```

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# Program to reverse the order of
    // the elements in the entire List<T>
    using System;
    using System.Collections;
    using System.Collections.Generic;

    class Geeks {

        // Main Method
        public static void Main()
        {

            // Creating an List<T> of Integers
            List<int> firstlist = new List<int>();

            // Adding elements to List
            for (int i = 1; i <= 5; i++) {
                firstlist.Add(i);
            }

            Console.WriteLine("Elements Present in List:");

            // Displaying the elements of List
            foreach(int k in firstlist)
            {
                Console.WriteLine(k);
            }

            Console.WriteLine(" ");

            Console.WriteLine("After Reversing: ");

            // using method Reverse()
            firstlist.Reverse();

            // Displaying the elements of List
            foreach(int k in firstlist)
            {
                Console.WriteLine(k);
            }
        }
    }
    ```

    **输出:**

    ```cs
    Elements Present in List:
    1
    2
    3
    4
    5

    After Reversing: 
    5
    4
    3
    2
    1

    ```

    **例 2:**

    ```cs
    // C# Program to reverse the order of
    // the elements in the entire List<T>
    using System;
    using System.Collections;
    using System.Collections.Generic;

    class Geeks {

        // Main Method
        public static void Main()
        {

            // Creating an List<T> of Integers
            List<string> firstlist = new List<string>();

            // Adding elements to List
            firstlist.Add("Geeks");
            firstlist.Add("C#");
            firstlist.Add("Java");
            firstlist.Add("C++");

            Console.WriteLine("Elements Present in List:");

            // Displaying the elements of List
            foreach(string k in firstlist)
            {
                Console.WriteLine(k);
            }

            Console.WriteLine(" ");

            Console.WriteLine("After Reversing: ");

            // using method Reverse()
            firstlist.Reverse();

            // Displaying the elements of List
            foreach(string k in firstlist)
            {
                Console.WriteLine(k);
            }
        }
    }
    ```

    **输出:**

    ```cs
    Elements Present in List:
    Geeks
    C#
    Java
    C++

    After Reversing: 
    C++
    Java
    C#
    Geeks

    ```

    #### 反向(Int32，Int32)方法

    此方法用于反转指定范围内元素的顺序。

    **语法:**

    ```cs
    public void Reverse (int index, int count);
    ```

    **参数:**

    > **指数:**是要反转的区间的从零开始的指数。
    > 
    > **计数:**是范围内要反转的元素个数。

    **异常:**

    *   **argumentoutofrangerexception:**如果*指数*或*计数*小于零。
    *   **参数异常:**如果*索引*和*计数*不表示列表中元素的有效范围< T >。

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# Program to reverse the order of
    // sub range in the List<T>
    using System;
    using System.Collections;
    using System.Collections.Generic;

    class Geeks {

        // Main Method
        public static void Main()
        {

            // Creating an List<T> of Integers
            List<string> firstlist = new List<string>();

            // Adding elements to List
            firstlist.Add("1st");
            firstlist.Add("2nd");
            firstlist.Add("3rd");
            firstlist.Add("4th");
            firstlist.Add("5th");
            firstlist.Add("6th");
            firstlist.Add("7th");

            Console.WriteLine("Elements Present in List:");

            // Displaying the elements of List
            foreach(string k in firstlist)
            {
                Console.WriteLine(k);
            }

            Console.WriteLine(" ");

            Console.WriteLine("After Reversing: ");

            // Reversing the sub-range
            // that starts from index 2
            // i.e 3rd element, and
            // count is 4 elements
            firstlist.Reverse(2, 4);

            // Displaying the elements of List
            foreach(string k in firstlist)
            {
                Console.WriteLine(k);
            }
        }
    }
    ```

    **输出:**

    ```cs
    Elements Present in List:
    1st
    2nd
    3rd
    4th
    5th
    6th
    7th

    After Reversing: 
    1st
    2nd
    6th
    5th
    4th
    3rd
    7th

    ```

    **例 2:**

    ```cs
    // C# Program to reverse the order of
    // sub range in the List<T>
    using System;
    using System.Collections;
    using System.Collections.Generic;

    class Geeks {

        // Main Method
        public static void Main()
        {

            // Creating an List<T> of Integers
            List<string> firstlist = new List<string>();

            // Adding elements to List
            firstlist.Add("1st");
            firstlist.Add("2nd");
            firstlist.Add("3rd");
            firstlist.Add("4th");
            firstlist.Add("5th");
            firstlist.Add("6th");
            firstlist.Add("7th");

            Console.WriteLine("Elements Present in List:");

            // Displaying the elements of List
            foreach(string k in firstlist)
            {
                Console.WriteLine(k);
            }

            Console.WriteLine(" ");

            Console.WriteLine("After Reversing: ");

            // taking negative index will give error
            firstlist.Reverse(-1, 4);

            // Displaying the elements of List
            foreach(string k in firstlist)
            {
                Console.WriteLine(k);
            }
        }
    }
    ```

    **时间错误：**

    > 未处理异常:
    > 系统。ArgumentOutOfRangeException:要求非负数。
    > 参数名称:索引

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . generic . list-1 . reverse？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1.reverse?view=netframework-4.7.2)**