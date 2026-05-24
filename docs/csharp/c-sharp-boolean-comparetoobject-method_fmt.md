# C# 布尔型 `CompareTo(Object)` 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-boolean-comparetoobject-method/](https://www.geeksforgeeks.org/c-sharp-boolean-comparetoobject-method/)

`Boolean.CompareTo(Object)` 方法用于将当前实例与指定的对象进行比较，并返回一个整数，该整数显示了它们之间的关系。

## 语法

```cs
public int CompareTo (object obj);
```

这里，需要一个对象来与当前实例或 `null` 进行比较。

## 返回值

该方法返回一个有符号整数，表示当前实例和 `obj` 的相对顺序。

*   **小于零：** 如果这个实例是 `false` 而 `obj` 是 `true`。
*   **零：** 如果这个实例和 `obj` 相等（要么两者都是 `true` 要么两者都是 `false`）。
*   **大于零：** 如果此实例为 `true` 而 `obj` 为 `false` 或 `null`。

## 异常

如果 `obj` 不是布尔值，它将抛出 `ArgumentException`。

## 例 1

```cs
// C# program to demonstrate the
// Boolean.CompareTo(Object) Method
using System;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring and initializing value1
            bool value1 = true;

            // Declaring and initializing value2
            object value2 = true;

            // using CompareTo() method
            int status = value1.CompareTo(value2);

            // checking the status
            if (status > 0)
                Console.WriteLine("{0} is greater than {1}",
                                    value1, value2);

            else if (status < 0)
                Console.WriteLine("{0} is less than {1}",
                                    value1, value2);
            else
                Console.WriteLine("{0} is equal to {1}",
                                    value1, value2);
        }

        catch (ArgumentException e) 
        {
            Console.WriteLine("value2 must be Boolean");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
True is equal to True
```

## 示例 2：适用于 `ArgumentException`

```cs
// C# program to demonstrate the
// Boolean.CompareTo(Object) Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        try {

            // Declaring and initializing value1
            bool value1 = true;

            // Declaring and initializing value2
            object value2 = 53554;

            // using CompareTo() method
            int status = value1.CompareTo(value2);

            // checking the status
            if (status > 0)
                Console.WriteLine("{0} is greater than {1}",
                                    value1, value2);

            else if (status < 0)
                Console.WriteLine("{0} is less than {1}",
                                    value1, value2);
            else
                Console.WriteLine("{0} is equal to {1}",
                                    value1, value2);
        }

        catch (ArgumentException e) 
        {
            Console.WriteLine("value2 must be Boolean");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
value2 must be Boolean
Exception Thrown: System.ArgumentException
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.boolean.compareto?view=netframework-4.8#System_Boolean_CompareTo_System_Object_](https://docs.microsoft.com/en-us/dotnet/api/system.boolean.compareto?view=netframework-4.8#System_Boolean_CompareTo_System_Object_)