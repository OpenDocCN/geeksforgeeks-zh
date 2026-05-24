# 类型。C# 中的 FindInterfaces()方法，带示例

> 原文:[https://www . geesforgeks . org/type-find interfaces-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/type-findinterfaces-method-in-c-sharp-with-examples/)

**类型。FindInterfaces(TypeFilter，Object)方法**用于返回一个*类型*对象的数组，该数组表示由当前*类型*实现或继承的接口的过滤列表。无论是由基类声明还是由这个类本身声明，在搜索过程中都会考虑这个类实现的所有接口。
该方法搜索基类层次结构，返回每个类实现的每个匹配接口以及每个接口实现的所有匹配接口(即返回匹配接口的传递闭包)。不会返回重复的接口。

**语法:**

> 公共虚拟类型[]查找接口(系统。反射。类型过滤器过滤器，对象过滤器标准)；

**参数:**

*   **筛选**:将接口与*筛选标准*进行比较的代表。
*   **过滤标准**:决定接口是否应该包含在返回数组中的搜索标准。

**返回值:**该方法返回一个*类型*对象的数组，表示当前类型实现或继承的接口的过滤列表，如果当前类型没有实现或继承匹配过滤器的接口，则返回类型类型的空数组。

**异常:**如果*过滤器*为空，该方法抛出**参数为空异常**。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# program to demonstrate the
// Type.FindInterfaces(TypeFilter,
// Object) Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {

        // Creating try-catch block 
        // to handle exceptions
        try {

            // Declaring and initializing 
            // object Type Datatype
            Type type = typeof(System.String);

            // Declaring and initializing the object 
            // of TypeFilter Datatype which help the
            // delegate that compares the interfaces 
            // against filterCriteria
            TypeFilter myFilter = new TypeFilter(MyInterfaceFilter);

            // Declaring and initializing filterCriteria 
            // object. It is used to search the criteria 
            // that determines whether an interface should
            // be included in the returned array.
            object filterCriteria = "System.Collections.IEnumerable";

            // Getting the filtered list of interface
            // using FindInterfaces() method
            Type[] myInterfaces = type.FindInterfaces(myFilter,
                                               filterCriteria);

            // Display the interfaces
            for (int j = 0; j < myInterfaces.Length; j++)
                Console.WriteLine("filtered list of interface : {0}.",
                                          myInterfaces[j].ToString());
        }

        // catch ArgumentNullException here
        catch (ArgumentNullException e) 
        {
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }

    // Defining MyInterfaceFilter
    // which helps to fix the certain 
    // condition on which filtration
    // took place
    public static bool MyInterfaceFilter(Type typeObj,
                                   Object criteriaObj)
    {
        if (typeObj.ToString() == criteriaObj.ToString())
            return true;
        else
            return false;
    }
}
```

**Output:**

```cs
filtered list of interface : System.Collections.IEnumerable.

```

**例 2:**

```cs
// C# program to demonstrate the
// Type.FindInterfaces(TypeFilter,
// Object) Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {
        // Creating try-catch block 
        // to handle exceptions
        try {

            // Declaring and initializing 
            // object Type Datatype
            Type type = typeof(System.String);

            // Declaring and initializing object 
            // of TypeFilter Datatype
            // which help the delegate that compares
            // the interfaces against filterCriteria.
            TypeFilter myFilter = null;

            // Declaring and initializing filterCriteria 
            // object. It is used to search the criteria 
            // that determines whether an interface should
            // be included in the returned array.
            object filterCriteria = "System.Collections.IEnumerable";

            // Getting the filtered list of interface
            // using FindInterfaces() method
            Type[] myInterfaces = type.FindInterfaces(myFilter,
                                               filterCriteria);

            // Display the interfaces
            for (int j = 0; j < myInterfaces.Length; j++)
                Console.WriteLine("filtered list of interface : {0}.",
                                          myInterfaces[j].ToString());
        }

        // catch ArgumentNullException here
        catch (ArgumentNullException e) 
       {
            Console.WriteLine("myFilter should not be null");
            Console.Write("Exception Thrown: ");
            Console.Write("{0}", e.GetType(), e.Message);
        }
    }
}
```

**Output:**

```cs
myFilter should not be null
Exception Thrown: System.ArgumentNullException

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . find interfaces？view=netcore-3.0](https://docs.microsoft.com/en-us/dotnet/api/system.type.findinterfaces?view=netcore-3.0)