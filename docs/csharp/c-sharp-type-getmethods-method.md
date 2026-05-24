# C# |类型。GetMethods()方法

> 原文:[https://www . geesforgeks . org/c-sharp-type-getmethods-method/](https://www.geeksforgeeks.org/c-sharp-type-getmethods-method/)

**类型。GetMethods()方法**用于获取当前类型的方法。此方法的重载列表中有 2 种方法，如下所示:

*   **方法***   **GetMethods() Method

    #### 方法

    当在派生类中被重写时，使用指定的绑定约束，此方法用于搜索为当前类型定义的方法。

    > **语法:**公共抽象系统。反射。方法信息[]获取方法(系统。反射. binding flags binding attr)；
    > 这里，需要一个由一个或多个 BindingFlags 组成的位掩码来返回一个空数组，binding flags 指定如何进行搜索，或者
    > Zero(默认值)。
    > 
    > **返回值:**此方法返回 MethodInfo 对象的数组，表示为当前类型定义的符合指定绑定约束的所有方法，或者返回 MethodInfo 类型的空数组，如果没有为当前类型定义方法，或者没有定义的方法符合绑定约束。

    以下程序说明了**类型的使用。GetMethods(BindingFlags)** 方法:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Type.GetMethods() Method
    using System;
    using System.Globalization;
    using System.Reflection;

    // Defining class Empty
    public class Empty { }

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing object of Type
            Type objType = typeof(Empty);

            // try-catch block for handling Exception
            try {

                // Getting array of Method by
                // using GetMethods() Method
                MethodInfo[] info = objType.GetMethods(BindingFlags.Public | BindingFlags.Instance);

                // Display the Result
                Console.WriteLine("Methods of current type is as Follow: ");
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
    ```

    **Output:**

    ```cs
    Methods of current type is as Follow: 
     Boolean Equals(System.Object)
     Int32 GetHashCode()
     System.Type GetType()
     System.String ToString()

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Type.GetMethods() Method
    using System;
    using System.Globalization;
    using System.Reflection;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing object of Type
            Type objType = typeof(int);

            // try-catch block for handling Exception
            try {

                // Getting array of Method by
                // using GetMethods() Method
                MethodInfo[] info = objType.GetMethods(BindingFlags.Public | BindingFlags.Static);

                // Display the Result
                Console.WriteLine("Methods of current type is as Follow: ");
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
    ```

    **Output:**

    ```cs
    Methods of current type is as Follow: 
     Int32 Parse(System.String)
     Int32 Parse(System.String, System.Globalization.NumberStyles)
     Int32 Parse(System.String, System.IFormatProvider)
     Int32 Parse(System.String, System.Globalization.NumberStyles, System.IFormatProvider)
     Boolean TryParse(System.String, Int32 ByRef)
     Boolean TryParse(System.String, System.Globalization.NumberStyles, System.IFormatProvider, Int32 ByRef)

    ```

    #### GetMethods()方法

    此方法用于返回当前类型的所有公共方法。

    > **语法:**公共系统。反射. method info[]GetMethods()；
    > 
    > **返回值:**此方法返回 MethodInfo 对象的数组，表示为当前类型定义的所有公共方法，如果没有为当前类型定义公共方法，则返回 MethodInfo 类型的空数组。

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Type.GetMethods() Method
    using System;
    using System.Globalization;
    using System.Reflection;

    // Defining class Empty
    class Empty { }

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing object of Type
            Type objType = typeof(Empty);

            // try-catch block for handling Exception
            try {

                // Getting array of Method by
                // using GetMethods() Method
                MethodInfo[] info = objType.GetMethods();

                // Display the Result
                Console.WriteLine("Methods of current type is as Follow: ");
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
    ```

    **Output:**

    ```cs
    Methods of current type is as Follow: 
     Boolean Equals(System.Object)
     Int32 GetHashCode()
     System.Type GetType()
     System.String ToString()

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Type.GetMethods() Method
    using System;
    using System.Globalization;
    using System.Reflection;

    // Defining class Student
    public class Student {

        private string name, dept;
        private int roll;

        // Constructor
        public Student(string name, int roll, string dept)
        {
            this.name = name;
            this.roll = roll;
            this.dept = dept;
        }

        // getter for name
        public string getName()
        {
            return name;
        }

        // getter for roll
        public int getRoll()
        {
            return roll;
        }

        // getter for dept
        public string getDept()
        {
            return dept;
        }
    }

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing object of Type
            Type objType = typeof(Student);

            // try-catch block for handling Exception
            try {

                // Getting array of Method by
                // using GetMethods() Method
                MethodInfo[] info = objType.GetMethods(BindingFlags.Public | BindingFlags.Instance);

                // Display the Result
                Console.WriteLine("Methods of current type is as Follow: ");
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
    ```

    **Output:**

    ```cs
    Methods of current type is as Follow: 
     System.String getName()
     Int32 getRoll()
     System.String getDept()
     Boolean Equals(System.Object)
     Int32 GetHashCode()
     System.Type GetType()
     System.String ToString()

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . getmethods？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.getmethods?view=netframework-4.8)**