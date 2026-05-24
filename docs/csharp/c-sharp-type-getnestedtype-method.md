# C# |类型。GetNestedType()方法

> 原文:[https://www . geesforgeks . org/c-sharp-type-getnestedtype-method/](https://www.geeksforgeeks.org/c-sharp-type-getnestedtype-method/)

**类型。GetNestedType()方法**用于获取嵌套在当前类型中的特定类型。此方法的重载列表中有 2 种方法，如下所示:

*   **方法***   **GetNestedType(String) Method

    #### 方法

    当在派生类中重写时，使用指定的绑定约束，此方法用于搜索指定的嵌套类型。

    > **语法:**公共抽象类型 GetNestedType(字符串名，System。反射. binding flags binding attr)；
    > 
    > **参数** :
    > **名称**:包含要获取的嵌套类型名称的字符串。
    > **bindingAttr** :一个由一个或多个 BindingFlags 组成的位掩码，指定如何进行搜索或归零，以返回空值。

    **返回值:**这个方法返回一个表示嵌套类型的对象，如果找到匹配指定的需求；否则，为 null。

    **异常**:如果名称为空，该方法抛出**参数为空异常**。

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Type.GetNestedType(String, 
    // BindingFlags) Method
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
            Type objType = typeof(Person);

            // try-catch block for handling Exception
            try {

                Type type = objType.GetNestedType("Student",
                   BindingFlags.Public | BindingFlags.Instance);

                // Display the Result
                Console.Write("NestedType of current type is: ");
                Console.WriteLine(" {0}", type);
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

    public class Person {

        public class Student {

            // string name;
            // int roll;
            // string dept;
        }

        public class Teacher {

            // string name;
            // string dept;
            // int id;
        }
    }
    ```

    **Output:**

    ```cs
    NestedType of current type is:  Person+Student

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Type.GetNestedType(String, 
    // BindingFlags) Method
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
            Type objType = typeof(Person);

            // try-catch block for handling Exception
            try {

                Type type = objType.GetNestedType(null,
                   BindingFlags.Public | BindingFlags.Instance);

                // Display the Result
                Console.Write("NestedType of current type is: ");
                Console.WriteLine(" {0}", type);
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

    // Defining Person class
    public class Person {

        // Defining class Student
        public class Student {

            // string name;
            // int roll;
            // string dept;
        }

        // Defining class Teacher
        public class Teacher {

            // string name;
            // string dept;
            // int id;
        }
    }
    ```

    **Output:**

    ```cs
    name is null.
    Exception Thrown: System.ArgumentNullException

    ```

    #### GetNestedType(字符串)方法

    此方法用于搜索具有指定名称的公共嵌套类型。

    > **语法:** public Type GetNestedType(字符串名称)；
    > 在这里，它获取包含嵌套类型名称的字符串。
    > 
    > **返回值:**该方法返回一个表示公共嵌套类型的对象，如果找到，则返回指定的名称；否则，为 null。
    > 
    > **异常**:如果名称为空，该方法抛出**参数为空异常**。

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Type.GetNestedType(String) Method
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
            Type objType = typeof(Person);

            // try-catch block for handling Exception
            try {

                Type type = objType.GetNestedType("Teacher");

                // Display the Result
                Console.Write("NestedType of current type is: ");
                Console.WriteLine(" {0}", type);
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

    // Defining Person class
    public class Person {

        // Defining class Student
        public class Student {

            // string name;
            // int roll;
            // string dept;
        }

        // Defining class Teacher
        public class Teacher {

            // string name;
            // string dept;
            // int id;
        }
    }
    ```

    **Output:**

    ```cs
    NestedType of current type is:  Person+Teacher

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Type.GetNestedType(String) 
    // Method
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
            Type objType = typeof(Person);

            // try-catch block for handling Exception
            try {

                Type type = objType.GetNestedType(null);

                // Display the Result
                Console.Write("NestedType of current type is: ");
                Console.WriteLine(" {0}", type);
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

    // Defining Person class
    public class Person {

        // Defining class Student
        public class Student {

            // string name;
            // int roll;
            // string dept;
        }

        // Defining class Teacher
        public class Teacher {

            // string name;
            // string dept;
            // int id;
        }
    }
    ```

    **Output:**

    ```cs
    name is null.
    Exception Thrown: System.ArgumentNullException

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . getnestedtype？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.getnestedtype?view=netframework-4.8)**