# C# |字符串 Concat 带示例| Set-1

> 原文:[https://www . geesforgeks . org/c-sharp-string-concat-with-examples-set-1/](https://www.geeksforgeeks.org/c-sharp-string-concat-with-examples-set-1/)

**弦。连接方法**用于连接一个或多个[字符串](https://www.geeksforgeeks.org/c-string/)的实例或一个或多个对象实例的值的[字符串](https://www.geeksforgeeks.org/c-string/)表示。它总是返回串联字符串。
这个方法可以通过传递不同类型和数量的参数来重载。Concat 方法的重载列表中总共有 **11 个**方法，其中 3 个在本文中讨论，其余的在 **Set-2、Set-3 和 Set-4** 中讨论。

1.  **串联(串、串、串、串)**
2.  **连接(对象，对象，对象，对象)**
3.  **连接(对象，对象，对象)**
4.  **连接（字符串，字符串）**
5.  **串联(字符串，字符串，字符串)**
6.  **连接（字符串[]）**
7.  **Concat(Object[])**
8.  **连接(对象)**
9.  **连接(对象，对象)**
10.  <串>串
11.  **Concat<T>(IEnumerable<T>)**

    ##### 1\. 连接（字符串，字符串，字符串，字符串）

    此方法用于将四个不同的字符串连接成一个字符串。您也可以使用连接运算符( **+** )来连接字符串。

    **注意:**如果数组包含空对象，则使用空字符串代替空对象。

    **语法:**

    ```cs
    public static string Concat (string strA, string strB, string strC, string strD);
    ```

    **参数:**

    > **strA:** 要连接的第一个字符串。
    > 
    > **strB:** 要连接的第二个字符串。
    > 
    > **strC:** 要连接的第三个字符串。
    > 
    > **strD:** 要连接的第四个字符串。
    > 
    > 所有这些参数的类型都是**系统。弦**。

    **返回值:**该方法的返回类型为**系统。弦**。该方法返回一个由四个字符串串联而成的字符串，即 *strA* 、 *strB* 、 *strC* 和 *strD* 。

    **示例:**

    ```cs
    // C# program to illustrate the use of 
    // Concat(String, String, String, String) Method
    using System;

    class GFG {

        // Main Method
        static public void Main()
        {
            string strA = "Welcome ";
            string strB = "to ";
            string strC = "GFG ";
            string strD = "Portal.";
            string str;

            // print all strings
            Console.WriteLine("String A is: {0}", strA);
            Console.WriteLine("String B is: {0}", strB);
            Console.WriteLine("String C is: {0}", strC);
            Console.WriteLine("String D is: {0}", strD);

            // Concatenate four different strings
            // into a single String using the 
            // Concat(String, String, String, String) Method
            str = String.Concat(strA, strB, strC, strD);

            Console.WriteLine("Concatenated string is: {0}", str);
        }
    }
    ```

    **输出:**

    ```cs
    String A is: Welcome 
    String B is: to 
    String C is: GFG 
    String D is: Portal.
    Concatenated string is: Welcome to GFG Portal.

    ```

    ##### 2.连接(对象，对象，对象，对象)

    此方法用于连接四个指定对象和可选可变长度参数列表中指定的任何对象的字符串表示形式。

    **注意:**如果该方法中存在空参数，则*字符串。空*用于代替空参数。

    **语法:**

    ```cs
    public static string Concat (object argA, object argB, object argC, object argD);
    ```

    **参数:**

    > **argA:** 第一个要连接的对象。
    > **argB:** 第二个要连接的对象。
    > **argC:** 要连接的第三个对象。
    > **argD:** 第四个要连接的对象。

    **返回值:**该方法的返回类型为**系统。弦**。它返回串联字符串，该字符串表示参数列表中的每个值。

    **示例:**

    ```cs
    // C# program to illustrate the use of 
    // Concat(object, object, object, object) Method
    using System;

    class GFG {

        // Main method
        public static void Main()
        {

            // string
            string strA = "Hello! ";

            // object
            object ob = strA;

            // object array
            Object[] objs = new Object[] {"Black", " Blue"};

            // Concatenating four objects by using the
            // Concat(object, object, object, object) method
            Console.WriteLine("Concatenate four objects: {0}",
                                 String.Concat(ob, ob, ob, ob));

            Console.WriteLine("Concatenate two element object array: {0}", 
                                                    String.Concat(objs));
        }
    }
    ```

    **输出:**

    ```cs
    Concatenate four objects: Hello! Hello! Hello! Hello! 
    Concatenate two element object array: Black Blue

    ```

    ##### 3.连接(对象，对象，对象)

    此方法用于连接三个指定对象的字符串表示形式。如果该方法中存在空参数，则*字符串。空*用于代替空参数。

    **语法:**

    ```cs
    public static string Concat (object argA, object argB, object argC);
    ```

    **注意:**该方法通过调用每个对象的无参数 *ToString* 方法来串联 argA、argB 和 argC，并且不添加任何分隔符。

    **参数:**

    > **argA:** 第一个要连接的对象。
    > **argB:** 第二个要连接的对象。
    > **argC:** 要连接的第三个对象。

    **返回值:**该方法的返回类型为**系统。弦**。此方法返回一个串联字符串，它是参数列表中每个值的表示形式。

    **示例:**

    ```cs
    // C# program to illustrate the use of 
    // Concat(object, object, object) Method
    using System;

    class GFG {

        // Main method
        public static void Main()
        {

            // string
            string strA = "GFG ";

            // object
            object ob = strA;

            // Concatenating three objects by using
            // Concat(object, object, object) method
            Console.WriteLine("Concatenate three objects : {0}",
                                     String.Concat(ob, ob, ob));
        }
    }
    ```

    **输出:**

    ```cs
    Concatenate three objects : GFG GFG GFG 

    ```

    **下一个:** [第二集](https://www.geeksforgeeks.org/c-string-concat-with-examples-set-2/)，第三集

    **参考:**T2？视图=netframework-4.7.2