# C# |类型。获取属性()方法

> 原文:[https://www . geesforgeks . org/c-sharp-type-get properties-method/](https://www.geeksforgeeks.org/c-sharp-type-getproperties-method/)

**类型。获取属性()方法**用于获取当前类型的属性。此方法的重载列表中有 2 种方法，如下所示:

*   **GetProperties()方法***   **GetProperties(BindingFlags) Method

    #### GetProperties()方法

    此方法用于返回当前类型的所有公共属性。

    > **语法:**公共系统。反射. property info[]GetProperties()；
    > 
    > **返回值:**此方法返回一个 PropertyInfo 对象数组，表示当前类型的所有公共属性，如果当前类型没有公共属性，则返回 PropertyInfo 类型的空数组。

    以下程序说明了**类型的使用。GetProperties()** 方法:

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Type.GetProperties() Method
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
            Type objType = typeof(string);

            // try-catch block for handling Exception
            try {

                // using GetProperties() Method
                PropertyInfo[] type = objType.GetProperties();

                // Display the Result
                Console.WriteLine("Properties of current type is: ");
                for (int i = 0; i < type.Length; i++)
                    Console.WriteLine(" {0}", type[i]);
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
    Properties of current type is: 
     Int32 Length
     Char Chars [Int32]

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Type.GetProperties() Method
    using System;
    using System.Globalization;
    using System.Reflection;

    // Defining class Empty
    public class Empty {}

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing object of Type
            Type objType = typeof(System.Type);

            // try-catch block for handling Exception
            try {

                // using GetProperties() Method
                PropertyInfo[] type = objType.GetProperties();

                // Display the Result
                Console.WriteLine("Properties of current type is: ");
                for (int i = 0; i < 10; i++)
                    Console.WriteLine(" {0}", type[i]);
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
    Properties of current type is: 
     System.Reflection.MemberTypes MemberType
     System.Type DeclaringType
     System.Reflection.MethodBase DeclaringMethod
     System.Type ReflectedType
     System.Runtime.InteropServices.StructLayoutAttribute StructLayoutAttribute
     System.Guid GUID
     System.Reflection.Binder DefaultBinder
     System.Reflection.Module Module
     System.Reflection.Assembly Assembly
     System.RuntimeTypeHandle TypeHandle

    ```

    #### 获取属性(绑定标签)方法

    当在派生类中被重写时，使用指定的绑定约束，此方法用于搜索当前类型的属性。

    > **语法:**公共抽象系统。反射。属性信息[]获取属性(系统。反射. binding flags binding attr)；
    > 这里，它需要一个由一个或多个 BindingFlags 组成的位掩码来返回 null，binding flags 指定如何执行搜索或 Zero。
    > 
    > **返回值:**如果当前类型没有属性，或者没有属性匹配绑定约束，则该方法返回一个 PropertyInfo 对象的数组，该数组表示当前类型中匹配指定绑定约束的所有属性，或者返回一个 PropertyInfo 类型的空数组。

    **例 1:**

    ```cs
    // C# program to demonstrate the
    // Type.GetProperties(BindingFlags)
    // Method
    using System;
    using System.Globalization;
    using System.Reflection;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing object of Type
            Type objType = typeof(Dog);

            // using GetProperties() Method
            PropertyInfo[] type = objType.GetProperties(BindingFlags.Instance | BindingFlags.Public);

            // Display the Result
            Console.WriteLine("Properties of current type is: ");
            for (int i = 0; i < type.Length; i++)
                Console.WriteLine(" {0}", type[i]);
        }
    }

    // Defining class Dog
    public class Dog {

        private string color, breed, type;

        // Constructor
        public Dog(string color, string breed, string type)
        {
            this.color = color;
            this.breed = breed;
            this.type = type;
        }

        // Color Property
        public String Color
        {
            get { return color; }
        }

        // Breed Property
        public String Breed
        {
            get { return breed; }
        }

        // Type Property
        public String Type
        {
            get { return type; }
        }

        // BloodGroup Property
        private String BloodGroup
        {
            get { return "AB+"; }
        }
    }
    ```

    **Output:**

    ```cs
    Properties of current type is: 
     System.String Color
     System.String Breed
     System.String Type

    ```

    **例 2:**

    ```cs
    // C# program to demonstrate the
    // Type.GetProperties(BindingFlags)
    // Method
    using System;
    using System.Globalization;
    using System.Reflection;

    class GFG {

        // Main Method
        public static void Main()
        {
            // Declaring and initializing object of Type
            Type objType = typeof(Dog);

            // using GetProperties() Method
            PropertyInfo[] type = objType.GetProperties(BindingFlags.Instance | BindingFlags.NonPublic);

            // Display the Result
            Console.WriteLine("Properties of current type is: ");
            for (int i = 0; i < type.Length; i++)
                Console.WriteLine(" {0}", type[i]);
        }
    }

    // Defining class Dog
    public class Dog {

        private string color, breed, type, bp;

        // Constructor
        public Dog(string color, string breed,
                       string type, string bp)
        {
            this.color = color;
            this.breed = breed;
            this.type = type;
            this.bp = bp;
        }

        // Color Property
        public String Color
        {
            get { return color; }
        }

        // Breed Property
        public String Breed
        {
            get { return breed; }
        }

        // Type Property
        public String Type
        {
            get { return type; }
        }

        // BloodGroup Property
        protected String BloodGroup
        {
            get { return "AB+"; }
        }

        // BloodPressure Property
        protected String BloodPressure
        {
            get { return bp; }
        }
    }
    ```

    **Output:**

    ```cs
    Properties of current type is: 
     System.String BloodGroup
     System.String BloodPressure

    ```

    **参考:**

    *   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . getproperties？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.getproperties?view=netframework-4.8)**