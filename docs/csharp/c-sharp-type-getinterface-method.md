# C# |类型。GetInterface()方法

> 原文:[https://www . geesforgeks . org/c-sharp-type-getinterface-method/](https://www.geeksforgeeks.org/c-sharp-type-getinterface-method/)

**类型。GetInterface()方法**用于获取当前类型实现或继承的特定接口。

*   **GetInterface(字符串)方法**
*   **GetInterface(字符串，布尔)方法**

#### **GetInterface(字符串)方法**

**此方法用于搜索具有指定名称的接口。**

> ****语法:**公共类型 GetInterface(字符串名称)；
> 这里，需要包含接口名称的字符串来获取。对于通用接口，这是一个混乱的名称。**
> 
> ****返回值:**该方法返回一个对象，该对象代表具有指定名称的接口，由当前类型实现或继承，否则为空。**
> 
>  ****异常:**如果名称为空，该方法抛出 *ArgumentNullException* 。**

**以下程序说明了**类型的使用。GetInterface(字符串)**方法:**

****例 1:****

```cs
// C# program to demonstrate the
// Type.GetInterface(String) Method
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

            // Getting interface of specified name
            // using GetField(String) Method
            Type minterface = objType.GetInterface("IFormattable");

            // Display the Result
            Console.WriteLine("interface is: {0}", minterface);
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

****Output:**

```cs
interface is: System.IFormattable

```** 

****示例 2:** 适用于*参数异常***

```cs
// C# program to demonstrate the
// Type.GetInterface(String) Method
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

            // Getting interface of specified name
            // using GetField(String) Method
            Type minterface = objType.GetInterface(null);

            // Display the Result
            Console.WriteLine("interface is: {0}", minterface);
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

****Output:**

```cs
name is null.
Exception Thrown: System.ArgumentNullException

```** 

#### **GetInterface(字符串，布尔)方法**

**此方法用于搜索指定的接口，指定在派生类中重写时是否对接口名称进行不区分大小写的搜索。**

> ****语法:**公共抽象类型 GetInterface(字符串名称，bool ignore case)；**
> 
>  ****参数:**
> 
> **名称**:包含要获取的接口名称的字符串。对于通用接口，这是一个混乱的名称。
> 
> **忽略**:如果为 true，则忽略*名称中指定简单接口名称的部分*(指定名称空间的部分必须大小写正确)，如果为 false，则对名称的所有部分执行区分大小写的搜索。**

****返回值:**该方法返回 n 个代表指定名称接口的对象，由当前类型实现或继承，否则为空。**

****异常**:如果名称为空，该方法抛出**参数为空异常**。**

**以下程序说明了上述方法的使用:**

****例 1:****

```cs
// C# program to demonstrate the
// Type.GetInterface(String, 
// Boolean) Method
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

            // Getting interface of specified name
            // using GetField(String) Method
            Type minterface = objType.GetInterface("iformattable", true);

            // Display the Result
            Console.WriteLine("interface is: {0}", minterface);
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

****Output:**

```cs
interface is: System.IFormattable

```** 

****示例 2:** 适用于*参数异常***

```cs
// C# program to demonstrate the
// Type.GetInterface(String, 
// Boolean) Method
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

            // Getting interface of specified name
            // using GetField(String) Method
            Type minterface = objType.GetInterface(null, true);

            // Display the Result
            Console.WriteLine("interface is: {0}", minterface);
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

****输出:****

```cs
name is null.
Exception Thrown: System.ArgumentNullException 
```

****参考:****

*   **[https://docs . Microsoft . com/en-us/dotnet/API/system . type . getinterface？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.getinterface?view=netframework-4.8)**