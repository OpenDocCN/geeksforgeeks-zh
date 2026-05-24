# C# |类型。GetMember()方法

> 原文:[https://www . geesforgeks . org/c-sharp-type-get member-method/](https://www.geeksforgeeks.org/c-sharp-type-getmember-method/)

**类型。GetMember()方法**用于获取当前类型的指定成员。此方法的重载列表中有 3 种方法，如下所示:

*   **获取成员(字符串)方法***   **获取成员(字符串，绑定标签)方法***   **GetMember(String, MemberTypes, BindingFlags) Method

    #### 获取成员(字符串)方法

    此方法搜索具有指定名称的公共成员。

    > **语法:**公共系统。反射. MemberInfo[] GetMember(字符串名称)；
    > 在这里，它需要包含公共成员名称的字符串来获取。
    > 
    > **返回值:**这个方法返回一个 MemberInfo 对象的数组，表示具有指定名称的公共成员，如果没有找到，则返回一个空数组。
    > 
    > **异常:**如果名称为空，该方法抛出 **ArgumentNullException** 。

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Type.GetMember(String) Method
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

                MemberInfo[] info = objType.GetMember("Name");

                // Display the Result
                Console.WriteLine("Members of current type is as Follow: ");
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
    Members of current type is as Follow: 
     System.String Name

    ```

    **示例 2:** 适用于*参数异常*

    ```cs
    // C# program to demonstrate the
    // Type.GetMember(String) Method
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

                MemberInfo[] info = objType.GetMember(null);

                // Display the Result
                Console.WriteLine("Members of current type is as Follow: ");
                for (int i = 0; i < info.Length; i++)
                    Console.WriteLine(" {0}", info[i]);
            }

            // catch ArgumentNullException here
            catch (ArgumentNullException e)
            {
                Console.WriteLine("name is null.");
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
    name is null.
    Exception Thrown: System.ArgumentNullException

    ```

    #### 获取成员(字符串，绑定标签)方法

    此方法用于使用指定的绑定约束搜索指定的成员。

    > **语法:**公共虚拟系统。反射。成员信息[]获取成员(字符串名称，系统。反射. binding flags binding attr)；
    > 
    > **参数** :
    > **名称**:是包含要获取的成员名称的字符串。
    > **bindingAttr** :它是一个位掩码，由一个或多个 BindingFlags 组成，指定如何进行搜索。或者，零，返回一个空数组。
    > 
    > **返回值:**这个方法返回一个 MemberInfo 对象的数组，表示具有指定名称的公共成员，如果没有找到，则返回一个空数组。
    > 
    > **异常**:如果名称为空，该方法抛出**参数为空异常**。

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Type.GetMember(String, BindingFlags) 
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

            // try-catch block for handling Exception
            try {

                MemberInfo[] info = objType.GetMember("Name",
                          BindingFlags.Public | BindingFlags.Instance);

                // Display the Result
                Console.WriteLine("Members of current type is as Follow: ");
                for (int i = 0; i < info.Length; i++)
                    Console.WriteLine(" {0}", info[i]);
            }

            // catch ArgumentNullException here
            catch (ArgumentNullException e)
            {
                Console.WriteLine("name is null.");
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
    Members of current type is as Follow: 
     System.String Name

    ```

    **示例 2:** 适用于*参数异常*

    ```cs
    // C# program to demonstrate the
    // Type.GetMember(String, BindingFlags) Method
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

                MemberInfo[] info = objType.GetMember(null,
                        BindingFlags.Public | BindingFlags.Instance);

                // Display the Result
                Console.WriteLine("Members of current type is as Follow: ");
                for (int i = 0; i < info.Length; i++)
                    Console.WriteLine(" {0}", info[i]);
            }

            // catch ArgumentNullException here
            catch (ArgumentNullException e) 
            {
                Console.WriteLine("name is null.");
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
    name is null.
    Exception Thrown: System.ArgumentNullException

    ```

    #### 获取成员(字符串、成员类型、绑定标签)方法

    此方法用于使用指定的绑定约束搜索指定成员类型的指定成员。

    > **语法:**公共虚拟系统。反射。成员信息[]获取成员(字符串名称，系统。反射。成员类型类型，系统。反射. binding flags binding attr)；
    > 
    > **参数** :
    > **名称**:是包含要获取的成员名称的字符串。
    > **类型**:是要搜索的值。
    > **bindingAttr** :它是一个由一个或多个 BindingFlags 组成的位掩码，用于指定如何进行搜索，或者使用 Zero 返回一个空数组。
    > 
    > **返回值:**这个方法返回一个 MemberInfo 对象的数组，表示具有指定名称的公共成员，如果没有找到，则返回一个空数组。
    > 
    > **异常:**如果名称为空，这个方法抛出 **ArgumentNullException** 。

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Type.GetMember(String, MemberTypes,
    // BindingFlags) Method
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

                MemberInfo[] info = objType.GetMember("returnNull", MemberTypes.Method,
                                          BindingFlags.Public | BindingFlags.Instance);

                // Display the Result
                Console.WriteLine("Members of current type is as Follow: ");
                for (int i = 0; i < info.Length; i++)
                    Console.WriteLine(" {0}", info[i]);
            }

            // catch ArgumentNullException here
            catch (ArgumentNullException e)
            {
                Console.WriteLine("name is null.");
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

        public void returnNull() {}
    }
    ```

    **Output:**

    ```cs
    Members of current type is as Follow: 
     Void returnNull()

    ```

    **示例 2:** 适用于*参数异常*

    ```cs
    // C# program to demonstrate the
    // Type.GetMember(String, MemberTypes,
    // BindingFlags) Method
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

                MemberInfo[] info = objType.GetMember(null, MemberTypes.Method,
                                  BindingFlags.Public | BindingFlags.Instance);

                // Display the Result
                Console.WriteLine("Members of current type is as Follow: ");
                for (int i = 0; i < info.Length; i++)
                    Console.WriteLine(" {0}", info[i]);
            }

            // catch ArgumentNullException here
            catch (ArgumentNullException e) 
            {
                Console.WriteLine("name is null.");
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

        public void returnNull() {}
    }
    ```

    **Output:**

    ```cs
    name is null.
    Exception Thrown: System.ArgumentNullException

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . getmember？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.getmember?view=netframework-4.8)**