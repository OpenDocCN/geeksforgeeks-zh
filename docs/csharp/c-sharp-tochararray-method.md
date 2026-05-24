# C# | ToCharArray()方法

> 原文:[https://www.geeksforgeeks.org/c-sharp-tochararray-method/](https://www.geeksforgeeks.org/c-sharp-tochararray-method/)

在 C# 中 ***ToCharArray()*** 是一个字符串方法。此方法用于将当前实例中的*指定字符串*的字符复制到 Unicode 字符数组，或将当前实例中的*指定子字符串*的字符复制到 Unicode 字符数组。通过更改传递给该方法的参数数量，可以重载该方法。

**语法:**

```cs
public char[] ToCharArray()
or
public char[] ToCharArray(int startIndex, int length)

```

**说明:**

*   **公共 char[] ToCharArray()** 方法不取参数。此方法将返回字符数组。字符数组元素将包含字符串的各个字符。所以基本上这个方法会将字符串的每个字符复制到字符数组中。字符串的第一个字符将在字符数组的索引 0 处复制，最后一个字符将在索引数组处复制。长度–1。当我们从字符数组中的字符创建一个字符串时，它将调用 String(Char[])构造函数。
*   **public char[]to chararray(int startIndex，int length)** 方法会取两个参数 *startIndex* ，用来指定子串的起始位置，类型为 *System。Int32* 。另一个参数是*长度*，用于指定子串的长度，类型为*系统。Int32* 。startIndex 参数从零开始，这意味着字符串实例中第一个字符的索引可以为零。

**要点:**

*   **公共 char[]to chararray(int startIndex，int length)** 如果 startIndex 或 length 小于零或(startIndex + length)大于当前字符串实例的长度，则方法可以给出异常*argumentoutofrangerexception*。
*   如果指定的长度为零，则返回的数组将为空并且长度为零。如果当前或此实例为 null 或空字符串("")，则返回的数组将为空，长度为零。

以下是演示上述方法的程序:

*   **程序一:**说明 **ToCharArray()** 方法:

    ```cs
    // C# program to demonstrate
    // ToCharArray() method
    using System;
    class Geeks {

        // Main Method
        public static void Main()
        {

            String str = "GeeksForGeeks";

            // copy the string str to chars 
            // character array & it will start
            // copy from 'G' to 's', i.e. 
            // beginning to ending of string
            char[] chars = str.ToCharArray();

            Console.WriteLine("String: " + str);
            Console.Write("Character array :");

            // to display the resulted character array
            for (int i = 0; i < chars.Length; i++)
                Console.Write(" " + chars[i]);
        }
    }
    ```

    **输出:**

    ```cs
    String: GeeksForGeeks
    Character array : G e e k s F o r G e e k s

    ```

*   **程序二:**说明 ToCharArray(int startIndex，int length)方法:

    ```cs
    // C# program to demonstrate
    // ToCharArray(int startIndex, int length)
    // method
    using System;
    class Geeks {

        // Main Method
        public static void Main()
        {
            String str = "GeeksForGeeks";

            // copy the string str to chars 
            // character array & it will 
            // start copy from 'F' to 'r' i.e.
            // copy from startindex of string
            // is 5 upto (startindex+length-1) i.e.
            // 5 + (3-1) has to copy
            char[] chars1 = str.ToCharArray(5, 3);

            Console.WriteLine("String: " + str);
            Console.WriteLine("\nCharacter array 1:");

            // to display the resulted character array
            for (int i = 0; i < chars1.Length; i++)
                Console.WriteLine("Index " + i + " : " + chars1[i]);

            // copy the string str to chars 
            // character array & it will 
            // start copy from 'F' to 'k' i.e.
            // copy from startindex of string
            // 5 upto (startindex+length-1) i.e.
            // 5 + (7-1)
            char[] chars2 = str.ToCharArray(5, 7);

            Console.Write("\nCharacter array 2:");

            // to display the resulted character 
            // array using foreach loop
            foreach(char c in chars2)
                Console.Write(" " + c);
        }
    }
    ```

    **输出:**

    ```cs
    String: GeeksForGeeks

    Character array 1:
    Index 0 : F
    Index 1 : o
    Index 2 : r

    Character array 2: F o r G e e k

    ```

**参考文献:**

*   [https://msdn . Microsoft . com/en-us/library/system . string . toraraarray 1](https://msdn.microsoft.com/en-us/library/ezftk57x(v=vs.110).aspx)
*   [https://msdn . Microsoft . com/en-us/library/system . string . toraraarray 2](https://msdn.microsoft.com/en-us/library/2c7h58e5(v=vs.110).aspx)