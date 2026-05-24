# C# Type.GetInterface() 方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-type-getinterface-method/](https://www.geeksforgeeks.org/c-sharp-type-getinterface-method/)

`Type.GetInterface()` 方法用于获取当前类型实现或继承的特定接口。

*   `GetInterface(String)` 方法
*   `GetInterface(String, Boolean)` 方法

## GetInterface(String) 方法

此方法用于搜索具有指定名称的接口。

> **语法:** `public Type GetInterface(String name);`
> 这里，`name` 是包含要获取的接口名称的字符串。对于泛型接口，这是一个混乱的名称。
>
> **返回值:** 该方法返回一个代表具有指定名称的接口的对象，该接口由当前类型实现或继承，否则为 `null`。
>
> **异常:** 如果 `name` 为 `null`，该方法抛出 `ArgumentNullException`。

以下程序说明了 `Type.GetInterface(String)` 方法的使用：

### 示例 1

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
            // using GetInterface(String) Method
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

**输出:**

```cs
interface is: System.IFormattable
```

### 示例 2：适用于 `ArgumentNullException`

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
            // using GetInterface(String) Method
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

**输出:**

```cs
name is null.
Exception Thrown: System.ArgumentNullException
```

## GetInterface(String, Boolean) 方法

此方法用于搜索指定的接口，指定在派生类中重写时是否对接口名称进行不区分大小写的搜索。

> **语法:** `public Type GetInterface(String name, bool ignoreCase);`
>
> **参数:**
>
> **name**: 包含要获取的接口名称的字符串。对于泛型接口，这是一个混乱的名称。
>
> **ignoreCase**: 如果为 `true`，则忽略 `name` 中指定简单接口名称的部分（指定命名空间的部分必须大小写正确）；如果为 `false`，则对名称的所有部分执行区分大小写的搜索。
>
> **返回值:** 该方法返回一个代表指定名称接口的对象，该接口由当前类型实现或继承，否则为 `null`。
>
> **异常:** 如果 `name` 为 `null`，该方法抛出 `ArgumentNullException`。

以下程序说明了上述方法的使用：

### 示例 1

```cs
// C# program to demonstrate the
// Type.GetInterface(String, Boolean) Method
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
            // using GetInterface(String, Boolean) Method
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

**输出:**

```cs
interface is: System.IFormattable
```

### 示例 2：适用于 `ArgumentNullException`

```cs
// C# program to demonstrate the
// Type.GetInterface(String, Boolean) Method
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
            // using GetInterface(String, Boolean) Method
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

**输出:**

```cs
name is null.
Exception Thrown: System.ArgumentNullException
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.type.getinterface?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.getinterface?view=netframework-4.8)