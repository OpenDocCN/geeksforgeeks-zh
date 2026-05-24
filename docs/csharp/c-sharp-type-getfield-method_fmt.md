# C# | `Type.GetField()` 方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-type-getfield-method/](https://www.geeksforgeeks.org/c-sharp-type-getfield-method/)

`Type.GetField()` 方法用于获取当前类型的特定字段。此方法的重载列表中有 2 种方法，如下所示：

*   `GetField(String)` 方法
*   `GetField(String, BindingFlags)` 方法

## `GetField(String)` 方法

此方法用于搜索具有指定名称的公共字段。

> **语法:**
> ```cs
> public FieldInfo GetField(string name);
> ```
> 这里，`name` 是包含要获取的数据字段名称的字符串。
>
> **返回值:** 该方法返回一个表示具有指定名称的公共字段的 `FieldInfo` 对象，否则为 `null`。
>
> **异常:** 如果 `name` 为 `null`，该方法抛出 `ArgumentNullException`。

以下程序说明了 `Type.GetField()` 方法的使用：

### 示例 1

```cs
// C# program to demonstrate the
// Type.GetField(String) Method
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

            // Getting FieldInfo by
            // using GetField(String) Method
            FieldInfo info = objType.GetField("Name");

            // Display the Result
            Console.WriteLine("FieldInfo is: {0}", info);
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

**输出:**

```cs
FieldInfo is: System.String Name
```

### 示例 2：适用于 `ArgumentNullException`

```cs
// C# program to demonstrate the
// Type.GetField(String) Method
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

            // Getting FieldInfo by
            // using GetField() Method
            FieldInfo info = objType.GetField(null);

            // Display the Result
            Console.WriteLine("FieldInfo is: {0}", info);
        }

        // catch ArgumentNullException here
        catch (ArgumentNullException e)
        {
            Console.WriteLine("Name is null.");
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

**输出:**

```cs
name is null.
Exception Thrown: System.ArgumentNullException
```

## `GetField(String, BindingFlags)` 方法

此方法用于使用指定的绑定约束搜索指定的字段。

> **语法:**
> ```cs
> public FieldInfo GetField(string name, BindingFlags bindingAttr);
> ```
>
> **参数:**
> - `name`: 包含要获取的数据字段名称的字符串。
> - `bindingAttr`: 它是一个由一个或多个 `BindingFlags` 组成的位掩码，指定如何进行搜索，或者返回 `null` 的 `Zero`。
>
> **返回值:** 该方法返回一个 `FieldInfo` 对象，表示符合指定要求的字段，否则为 `null`。
>
> **异常:** 如果 `name` 为 `null`，该方法抛出 `ArgumentNullException`。

以下程序说明了上述方法的使用：

### 示例 1

```cs
// C# program to demonstrate the
// Type.GetField(String, BindingFlags) Method
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

            // You must specify either BindingFlags.Instance
            // or BindingFlags.Static
            // and Specify BindingFlags.Public
            // to include public fields in the search
            BindingFlags battr = BindingFlags.Public | BindingFlags.Instance;

            // Getting FieldInfo by
            // using GetField() Method
            FieldInfo info = objType.GetField("Name", battr);

            // Display the Result
            Console.WriteLine("FieldInfo is: {0}", info);
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

**输出:**

```cs
FieldInfo is: System.String Name
```

### 示例 2：适用于 `ArgumentNullException`

```cs
// C# program to demonstrate the
// Type.GetField(String, BindingFlags) Method
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

            // You must specify either BindingFlags.Instance 
            // or BindingFlags.Static
            // and Specify BindingFlags.Public
            // to include public fields in the search
            BindingFlags battr = BindingFlags.Public | BindingFlags.Instance;

            // Getting FieldInfo by
            // using GetField() Method
            FieldInfo info = objType.GetField(null, battr);

            // Display the Result
            Console.WriteLine("FieldInfo is: {0}", info);
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
}
```

**输出:**

```cs
name is null.
Exception Thrown: System.ArgumentNullException
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.type.getfield?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.getfield?view=netframework-4.8)