## C# 布尔型.Equals(Object)方法

> 原文：[`https://www.geeksforgeeks.org/c-sharp-boolean-equalsobject-method/`](https://www.geeksforgeeks.org/c-sharp-boolean-equalsobject-method/)

`Boolean.Equals(Object)`方法用于获取一个值，该值指示当前实例是否等于指定的对象。

> **语法：** `public override bool Equals(Object obj);`
> 这里，需要一个对象与当前实例进行比较。
>
> **返回值：** 如果`obj`是布尔值，并且与此实例具有相同的值，则此方法返回`true`，否则返回`false`。

以下程序说明了上述方法的使用：

### 示例 1

```cs
// C# program to demonstrate the
// Boolean.Equals(Object) Method
using System;

class GFG {

// Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        bool value1 = true;

        // Declaring and initializing value2
        object value2 = 2 / 78;

        // using Equals(object) method
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

**输出：**

```cs
True is not equal to 0
```

### 示例 2

```cs
// C# program to demonstrate the
// Boolean.Equals(Object) Method
using System;

class GFG {

// Main Method
    public static void Main()
    {
        // calling get() method
        get(true, 5);
        get(true, 4);
        get(false, false);
        get(true, true);
    }

    // defining get() method
    public static void get(bool value1,
                          object value2)
    {
        // using Equals(object) method
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

**输出：**

```cs
True is not equal to 5
True is not equal to 4
False is equal to False
True is equal to True
```

**参考：**

*   [`https://docs.microsoft.com/en-us/dotnet/api/system.boolean.equals?view=netframework-4.8#System_Boolean_Equals_System_Object_`](https://docs.microsoft.com/en-us/dotnet/api/system.boolean.equals?view=netframework-4.8#System_Boolean_Equals_System_Object_)