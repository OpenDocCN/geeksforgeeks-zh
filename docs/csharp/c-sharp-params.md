# C# |参数

> 原文:[https://www.geeksforgeeks.org/c-sharp-params/](https://www.geeksforgeeks.org/c-sharp-params/)

Params 是 [C# ](https://www.geeksforgeeks.org/introduction-to-c-sharp/) 中的重要关键词。它被用作一个参数，可以采用**可变参数数**。

**关于参数关键词的要点:**

*   当程序员不知道要使用的参数数量时，这很有用。
*   仅允许一个 params 关键字，并且在 Params 关键字之后的函数声明中不允许有其他 Params。
*   如果不传递任何参数，参数的长度将为零。

**举例:**说明 **params 关键字**的使用

*   Simple program to show the params keyword usage

    ```cs
    // C# program to illustrate the 
    // use of params keyword
    using System;
    namespace Examples {

    class Geeks {

        // function containing params parameters
        public static int Add(params int[] ListNumbers)
        {
            int total = 0;

            // foreach loop
            foreach(int i in ListNumbers) 
            {
                total += i;
            }
            return total;
        }

    // Driver Code    
    static void Main(string[] args)
    {

        // Calling function by passing 5
        // arguments as follows
        int y = Add(12,13,10,15,56);

        // Displaying result
        Console.WriteLine(y);
    }
    }
    }
    ```

    **输出:**

    ```cs
    106

    ```

    **说明:**不需要定义数组的大小，因为在上面的程序中使用 params 关键字，Integer 数据将会是这样的形式:
    list numbers
    【0】12
    【1】13
    【2】10
    【3】15
    【4】56

*   Object type Params will allow any type of arguments and any number of arguments as follows :

    ```cs
    // C# program to illustrate the 
    // use of object type params
    using System; 

    namespace Example2 {
    class Geeks {

            // function using object type params 
            public void result(params object[] array) 
            { 
                for (int i = 0; i < array.Length; i++) 
                { 

                    // Display result
                    Console.WriteLine(array[i]); 
                }     
            } 

        // Driver Code 
        static void Main(string[] args) 
        { 
            Geeks gfg = new Geeks(); 

            // Variable length arguments
            gfg.result("Geeks", "GFG",
                       "ProGeek Cup 2.0",
                            "G4G", "100");
        } 

    } 
    } 
    ```

    **输出:**

    ```cs
    Geeks
    GFG
    ProGeek Cup 2.0
    G4G
    100

    ```

    **说明:**在上面的程序中，对象类型 params 参数可以接受任何类型的数据和任意数量的参数。