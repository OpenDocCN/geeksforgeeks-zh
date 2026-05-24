# C# |类型。GetMembers()方法

> 原文:[https://www . geesforgeks . org/c-sharp-type-get members-method/](https://www.geeksforgeeks.org/c-sharp-type-getmembers-method/)

**类型。GetMembers()方法**用于获取当前类型的成员(属性、方法、字段、事件等)。此方法的重载列表中有 2 种方法，如下所示:

*   **GetMembers()方法***   **GetMembers(BindingFlags) Method

    #### GetMembers()方法

    此方法用于返回当前类型的所有公共成员。

    > **语法:**公共系统。反射. MemberInfo[]GetMembers()；
    > 
    > **返回值:**该方法返回一个 MemberInfo 对象数组，表示当前类型的所有公共成员，如果当前类型没有公共成员，则返回一个 MemberInfo 类型的空数组。

    以下程序说明了**类型的使用。GetMembers()** 方法:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Type.GetMember() Method
    using System;
    using System.Globalization;
    using System.Reflection;

    // Defining Empty class
    public class Empty { }

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing object of Type
            Type objType = typeof(Empty);

            // try-catch block for handling Exception
            try {

                // Getting array of MemberInfos by
                // using GetMembers() Method
                MemberInfo[] info = objType.GetMembers();

                // Display the Result
                Console.WriteLine("Fields of current type is as Follow: ");

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
    Fields of current type is as Follow: 
     Boolean Equals(System.Object)
     Int32 GetHashCode()
     System.Type GetType()
     System.String ToString()
     Void .ctor()

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Type.GetMember() Method
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

                // Getting array of MemberInfos by
                // using GetMembers() Method
                MemberInfo[] info = objType.GetMembers();

                // Display the Result
                Console.WriteLine("Fields of current type is as Follow: ");
                for (int i = 0; i < 6; i++)
                    Console.WriteLine(" {0}", info[i]);
            }

            // catch ArgumentNullException here
            catch (ArgumentNullException e) {
                Console.Write("name is null.");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    Fields of current type is as Follow: 
     Int32 CompareTo(System.Object)
     Int32 CompareTo(Int32)
     Boolean Equals(System.Object)
     Boolean Equals(Int32)
     Int32 GetHashCode()
     System.String ToString()

    ```

    #### 方法

    当在派生类中被重写时，使用指定的绑定约束，此方法用于搜索为当前类型定义的成员。

    > **语法:**公共抽象系统。反射。成员信息[]获取成员(系统。反射. binding flags binding attr)；
    > 这里，需要一个由一个或多个 BindingFlags 组成的位掩码来指定如何进行搜索，或者
    > Zero(默认值)来返回一个空数组。

    **返回值:**此方法返回一个 MemberInfo 对象数组，表示为当前类型定义的符合指定绑定约束的所有成员；如果没有为当前类型定义成员，或者没有定义的成员符合绑定约束，则返回一个 MemberInfo 类型的空数组。

    以下程序说明了上述方法的使用:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Type.GetMembers(BindingFlags)
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
            Type objType = typeof(Empty);

            // try-catch block for handling Exception
            try {

                // Getting array of Fields by
                // using GetField() Method
                MemberInfo[] info = objType.GetMembers(BindingFlags.Public
                                                       | BindingFlags.Instance);

                // Display the Result
                Console.WriteLine("Fields of current type is as Follow: ");
                for (int i = 0; i < info.Length; i++)
                    Console.WriteLine(" {0}", info[i]);
            }

            // catch ArgumentNullException here
            catch (ArgumentNullException e) {
                Console.WriteLine("name is null.");
                Console.Write("Exception Thrown: ");
                Console.Write("{0}", e.GetType(), e.Message);
            }
        }
    }
    ```

    **Output:**

    ```cs
    Fields of current type is as Follow: 
     Boolean Equals(System.Object)
     Int32 GetHashCode()
     System.Type GetType()
     System.String ToString()
     Void .ctor()

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Type.GetMembers(BindingFlags)
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
            Type objType = typeof(int);

            // try-catch block for handling Exception
            try {

                // Getting array of Fields by
                // using GetField() Method
                MemberInfo[] info = objType.GetMembers(BindingFlags.Public
                                                       | BindingFlags.Static);

                // Display the Result
                Console.WriteLine("Fields of current type is as Follow: ");
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
    ```

    **Output:**

    ```cs
    Fields of current type is as Follow: 
     Int32 Parse(System.String)
     Int32 Parse(System.String, System.Globalization.NumberStyles)
     Int32 Parse(System.String, System.IFormatProvider)
     Int32 Parse(System.String, System.Globalization.NumberStyles, System.IFormatProvider)
     Boolean TryParse(System.String, Int32 ByRef)
     Boolean TryParse(System.String, System.Globalization.NumberStyles, System.IFormatProvider, Int32 ByRef)
     System.Int32 MaxValue
     System.Int32 MinValue

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . getmembers？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.getmembers?view=netframework-4.8)**