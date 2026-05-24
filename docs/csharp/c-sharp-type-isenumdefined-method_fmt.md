# Type.IsEnumDefined(Object) 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-type-isenumdefined-method/](https://www.geeksforgeeks.org/c-sharp-type-isenumdefined-method/)

`Type.IsEnumDefined(Object)` 方法用于返回一个值，该值指示当前枚举类型中是否存在指定的值。

## 语法

```csharp
public virtual bool IsEnumDefined(object value);
```

**参数**：`value` 是需要检验的对象。

## 返回值

如果指定的值是当前枚举类型的成员，该方法返回 `true`，否则返回 `false`。

## 异常

*   `ArgumentException`：如果当前类型不是枚举。
*   `ArgumentNullException`：如果 `value` 为 `null`。
*   `InvalidOperationException`：如果 `value` 的类型不能是枚举的基础类型。

以下程序说明了 `Type.IsEnumDefined(Object)` 方法的使用：

### 例 1

```csharp
// C# program to demonstrate the
// Type.IsEnumDefined(Object) Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // defining enum enu
    public enum enu {A, B, C};

    // Main Method
    public static void Main()
    {

        // try-catch block for handling Exception
        try {

            // creating and initializing object Type
            object value = enu.A;

            // checking for the current enumeration type
            // by using IsEnumDefined() Method
            bool status = typeof(enu).IsEnumDefined(value);

            // display the result
            if (status)
                Console.WriteLine("specified value is a member"+
                            " of the current enumeration type");
            else
                Console.WriteLine("specified value is not"+
                " present in the current enumeration type");
        }

        // catch ArgumentNullException here
        catch (ArgumentNullException e) {

            Console.WriteLine("Object is null.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        // catch ArgumentNullException here
        catch (InvalidOperationException e) {

            Console.WriteLine("Object is null.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        // catch ArgumentException here
        catch (ArgumentException e) {

            Console.WriteLine("Object is null.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出：**

```csharp
specified value is a member of the current enumeration type
```

### 例 2

```csharp
// C# program to demonstrate the
// Type.IsEnumDefined(Object) Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // defining enum enu
    public enum enu {A, B, C};

    // Main Method
    public static void Main()
    {

        // try-catch block for handling Exception
        try {

            // creating and initializing object Type
            object value = enu.B;

            // checking for the current enumeration type
            // by using IsEnumDefined() Method
            bool status = typeof(int).IsEnumDefined(value);

            // display the result
            if (status)
                Console.WriteLine("specified value is a member"+
                            " of the current enumeration type");
            else
                Console.WriteLine("specified value is not"+
               " present in the current enumeration type");
        }

        // catch ArgumentNullException here
        catch (ArgumentNullException e) {

            Console.WriteLine("value is null.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        // catch ArgumentException here
        catch (ArgumentException e) {

            Console.WriteLine("The current type is not an enumeration.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出：**

```csharp
The current type is not an enumeration.
Exception Thrown: System.ArgumentException
```

### 例 3

```csharp
// C# program to demonstrate the
// Type.IsEnumDefined(Object) Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // defining enum enu
    public enum enu {A, B, C};

    // Main Method
    public static void Main()
    {

        // try-catch block for handling Exception
        try {

            // creating and initializing object Type
            object value = null;

            // checking for the current enumeration type
            // by using IsEnumDefined() Method
            bool status = typeof(enu).IsEnumDefined(value);

            // display the result
            if (status)
                Console.WriteLine("specified value is a member"+
                            " of the current enumeration type");
            else
                Console.WriteLine("specified value is not"+
                " present in the current enumeration type");
        }

        // catch ArgumentNullException here
        catch (ArgumentNullException e) {

            Console.WriteLine("value is null.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }

        // catch ArgumentException here
        catch (ArgumentException e) {

            Console.WriteLine("The current type is not an enumeration.");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**输出：**

```csharp
value is null.
Exception Thrown: System.ArgumentNullException
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.type.isenumdefined?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.isenumdefined?view=netframework-4.8)