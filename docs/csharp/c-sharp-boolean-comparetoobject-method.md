# C# |布尔型。比较(对象)方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-boolean-compare tobject-method/](https://www.geeksforgeeks.org/c-sharp-boolean-comparetoobject-method/)

**布尔。比较(对象)方法**用于将当前实例与指定的对象进行比较，并返回一个整数，该整数显示了它们之间的关系。

**语法:**

```cs
public int CompareTo (object obj);
```

这里，需要一个对象来与当前实例或 null 进行比较。

**返回值:**该方法返回一个有符号整数，表示当前实例和*对象*的相对顺序。

*   **小于零:**如果这个实例是*假*而 obj 是*真*。
*   **零:**如果这个实例和 obj 相等(要么两者都是*真*要么两者都是*假*)。
*   **大于零:**如果此实例为*真*而对象为*假*或*空*。

**异常:**如果*对象*不是布尔值，它将抛出*参数异常*。

**例 1:**

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

**示例 2:** 适用于*参数异常*

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

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . boolean . compare to？视图=网络框架-4.8 # 系统 _ 布尔 _ 比较 _ 系统 _ 对象 _](https://docs.microsoft.com/en-us/dotnet/api/system.boolean.compareto?view=netframework-4.8# System_Boolean_CompareTo_System_Object_)