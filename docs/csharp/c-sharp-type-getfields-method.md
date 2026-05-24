# C# |类型。GetFields()方法

> 原文:[https://www . geesforgeks . org/c-sharp-type-getfields-method/](https://www.geeksforgeeks.org/c-sharp-type-getfields-method/)

**类型。GetFields()方法**用于获取当前类型的字段。此方法的重载列表中有 2 种方法，如下所示:

*   **GetFields()方法***   **GetFields(BindingFlags) Method

    #### GetFields()方法

    此方法用于返回当前类型的所有公共字段。

    > **语法:**公共系统。反射. FieldInfo[]GetFields()；
    > 
    > **返回值:**该方法返回一个表示为当前类型定义的所有公共字段的*字段信息*对象的数组。或者，如果没有为当前类型定义公共字段，则为字段信息类型的空数组。

    以下程序说明了**类型的使用。GetFields()** 方法:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Type.GetFields() Method
    using System;
    using System.Globalization;
    using System.Reflection;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing object of Type
            Type objType = typeof(Student);

            // try-catch block for handling Exception
            try {

                // Getting array of Fields by
                // using GetField() Method
                FieldInfo[] info = objType.GetFields(BindingFlags.Public | BindingFlags.Static);

                // Display the Result
                Console.Write("Fields of current type is as Follow: ");
                for (int i = 0; i < info.Length; i++)
                    Console.WriteLine(" {0}", info[i]);
            }

            // catch ArgumentNullException here
            catch (ArgumentNullException e) 
            {
                Console.Write("name is null.");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }

    // Defining class Student
    public class Student
    {
        public string Name = "Rahul";
        public string Dept = "Electrical";
        public int Roll = 10;
        public static int id = 02;
    }
    ```

    **Output:**

    ```cs
    Fields of current type is as Follow:  System.Int32 id

    ```

    **例 2:** 对于*如果没有定义公共字段*

    ```cs
    // C# program to demonstrate the
    // Type.GetFields(String) Method
    using System;
    using System.Globalization;
    using System.Reflection;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing object of Type
            Type objType = typeof(Student);

            // try-catch block for handling Exception
            try {

                // Getting array of Fields by
                // using GetField() Method
                FieldInfo[] info = objType.GetFields();

                // Display the Result
                Console.Write("Public Fields of current type is as follow: ");
                if (info.Length != 0) 
                {
                    for (int i = 0; i < info.Length; i++)
                        Console.WriteLine(" {0}", info[i]);
                }
                else
                    Console.WriteLine("No public fields are defined for the current Type.");
            }

            // catch ArgumentNullException here
            catch (ArgumentNullException e) 
            {
                Console.Write("name is null.");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }

    // Defining class Student
    public class Student
    { }
    ```

    **Output:**

    ```cs
    Public Fields of current type is as follow: No public fields are defined for the current Type.

    ```

    #### 方法

    此方法用于搜索为当前类型定义的字段，当在派生类约束中重写时，使用指定的绑定。

    > **语法:**公共抽象系统。反射。字段信息[]获取字段(系统。反射. binding flags binding attr)；
    > 这里， *bindingAttr* 是一个由一个或多个 BindingFlags 组成的位掩码，指定如何进行搜索，或者返回 null 的 Zero。
    > 
    > **返回值:**该方法返回一个 FieldInfo 对象数组，该数组表示为当前类型定义的所有与指定绑定约束相匹配的字段。或者，如果没有为当前类型定义字段，或者定义的字段都不匹配绑定约束，则为类型 FieldInfo 的空数组。

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# program to demonstrate the 
    // Type.GetField(String) 
    // Method 
    using System; 
    using System.Globalization; 
    using System.Reflection; 

    class GFG { 

        // Main Method 
        public static void Main() 
        { 
            // Declaring and initializing object of Type 
            Type objType = typeof(Student);

            // Creating try-catch block for handling Exception 
            try { 

                // You must specify either BindingFlags.Instance or BindingFlags.Static
                // and Specify BindingFlags.Public 
                // to include public fields in the search.
                BindingFlags battr = BindingFlags.Public | BindingFlags.Instance;

                // Getting FieldInfo by  
                // using GetField() Method 
                FieldInfo info = objType.GetField("Name", battr); 

                // Display the Result 
                Console.WriteLine("FieldInfo is -  {0}",info); 
            } 

            // catch ArgumentNullException here 
            catch (ArgumentNullException e)  
            { 
                Console.Write("name is null."); 
                Console.Write("Exception Thrown: "); 
                Console.Write("{0}", e.GetType(), e.Message); 
            } 
        } 
    }

    // Defining class Student
    public class Student
    {
        public string Name = "Rahul";
        public string Dept = "Electrical";
        public int Roll = 10;
    }
    ```

    **Output:**

    ```cs
    FieldInfo is - System.String Name

    ```

    **示例 2:** 适用于*参数异常*

    ```cs
    // C# program to demonstrate the 
    // Type.GetFields(String) 
    // Method 
    using System; 
    using System.Globalization; 
    using System.Reflection; 

    class GFG { 

        // Main Method 
        public static void Main() 
        { 
            // Declaring and initializing object of Type 
            Type objType = typeof(Book);

            // Creating try-catch block for handling Exception 
            try { 

                // Getting array of Fields by  
                // using GetField() Method 
                FieldInfo[] info = objType.GetFields(BindingFlags.NonPublic | BindingFlags.Instance); 

                // Display the Result
                Console.WriteLine("Fields of current type is as follow :-");
                for(int i=0; i<info.Length; i++)
                Console.WriteLine(" {0}",info[i]); 
            } 

            // catch ArgumentNullException here 
            catch (ArgumentNullException e)  
            { 
                Console.Write("name is null."); 
                Console.Write("Exception Thrown: "); 
                Console.Write("{0}", e.GetType(), e.Message); 
            } 
        } 
    }

    // Defining class Student
    public class Book
    {
        public string Name = "Element of Physics";
        public string Author = "R.S. Agrwal";
        public static int Price = 500;
        private string metadata = "djdieeiie";

    }
    ```

    **Output:**

    ```cs
    FieldInfo is - System.String Name

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . getfield？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.getfields?view=netframework-4.8)**