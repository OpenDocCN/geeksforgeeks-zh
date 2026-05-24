# C# | Type.Equals() 方法

> 原文: [https://www.geeksforgeeks.org/c-sharp-type-equals-method/](https://www.geeksforgeeks.org/c-sharp-type-equals-method/)

`Type.Equals()` 方法用于检查当前类型的底层系统类型是否与指定对象或类型的底层系统类型相同。此方法的重载列表中有 2 种方法，如下所示:

*   `Equals(Type)` 方法
*   `Equals(Object)` 方法

## Type.Equals(Type) 方法

此方法用于检查当前类型的基础系统类型是否与指定类型的基础系统类型相同。

> **语法:** `public virtual bool Equals(Type o);`
> 这里 `o` 是其底层系统类型要与当前 `Type` 的底层系统类型进行比较的对象。
>
> **返回值:** 如果 `o` 的底层系统类型与当前 `Type` 的底层系统类型相同，则该方法返回 `true`，否则返回 `false`。

以下程序说明了 `Type.Equals()` 方法的使用:

### 例 1:

```cs
// C# program to demonstrate the
// Type.Equals(Type) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        Type value1 = typeof(System.String);

        // Declaring and initializing value2
        Type value2 = typeof(System.Int32);

        // using Equals(Type) method
        bool status = value1.Equals(value2);

        // checking the status
        if (status)
            Console.WriteLine("{0} is equal to {1}",
                                value1, value2);
        else
            Console.WriteLine("{0} is not equal to {1}",
                                value1, value2);
    }
}
```

**Output:**

```cs
System.String is not equal to System.Int32
```

### 例 2:

```cs
// C# program to demonstrate the
// Type.Equals(Type) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        get(typeof(System.String), typeof(System.String));
        get(typeof(System.String), typeof(System.Int32));
        get(typeof(System.Decimal), typeof(System.Double));
    }

    // defining get() method
    public static void get(Type value1,
                           Type value2)
    {
        // using Equals(Type) method
        bool status = value1.Equals(value2);

        // checking the status
        if (status)
            Console.WriteLine("{0} is equal to {1}",
                                value1, value2);
        else
            Console.WriteLine("{0} is not equal to {1}",
                                value1, value2);
    }
}
```

**Output:**

```cs
System.String is equal to System.String
System.String is not equal to System.Int32
System.Decimal is not equal to System.Double
```

## Type.Equals(Object) 方法

该方法用于检查当前定义的 `Type` 对象的底层系统类型是否与指定对象的底层系统类型完全相同。

> **语法:** `public override bool Equals(object obj);`
> 这里 `obj` 是其底层系统类型要与当前 `Type` 的底层系统类型进行比较的对象。为了使比较成功，对象必须能够被转换或转化为 `Type` 类型的对象。
>
> **返回值:** 如果 `obj` 的底层系统类型与当前类型的底层系统类型相同，则该方法返回 `true`，否则返回 `false`。如果 `obj` 为 `null`，或者无法转换为 `Type` 对象，此方法也会返回 `false`。

以下程序说明了上述方法的使用:

### 例 1:

```cs
// C# program to demonstrate the
// Type.Equals(Object) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        Type value1 = typeof(int);

        // Declaring and initializing value2
        object value2 = typeof(int);

        // using Equals(Object) method
        bool status = value1.Equals(value2);

        // checking the status
        if (status)
            Console.WriteLine("{0} is equal to {1}",
                                value1, value2);
        else
            Console.WriteLine("{0} is not equal to {1}",
                                value1, value2);
    }
}
```

**Output:**

```cs
System.Int32 is equal to System.Int32
```

### 例 2:

```cs
// C# program to demonstrate the
// Type.Equals(Object) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // calling get() method
        get(typeof(int), new Object());
        get(typeof(System.String), (object)5.5);
        get(typeof(System.String), null);
    }

    // defining get() method
    public static void get(Type value1,
                           object value2)
    {
        // using Equals(Object) method
        bool status = value1.Equals(value2);

        // checking the status
        if (status)
            Console.WriteLine("{0} is equal to {1}",
                                value1, value2);
        else
            Console.WriteLine("{0} is not equal to {1}",
                                value1, value2);
    }
}
```

**Output:**

```cs
System.Int32 is not equal to System.Object
System.String is not equal to 5.5
System.String is not equal to
```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.type.equals?view=netcore-3.0](https://docs.microsoft.com/en-us/dotnet/api/system.type.equals?view=netcore-3.0)