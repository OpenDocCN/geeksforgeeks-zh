# 什么是 C# 中的反射？

> 原文:[https://www . geeksforgeeks . org/什么是 c-sharp 中的反射/](https://www.geeksforgeeks.org/what-is-reflection-in-c-sharp/)

反射是描述代码中类型、方法和字段的元数据的过程。命名空间**系统。反射**使您能够获得关于加载的程序集、其中的元素(如类、方法和值类型)的数据。*系统的一些常用类。反思*有:

| 班级 | 描述 |
| 装配 | 描述一个程序集，它是公共语言运行时应用程序的可重用、可版本化且自我描述的构建块 |
| AssemblyName | 用唯一的名称标识程序集 |
| 建筑信息 | 描述类构造函数并提供对元数据的访问 |
| 方法信息 | 描述类方法并提供对其元数据的访问 |
| ParameterInfo | 描述方法的参数，并提供对其元数据的访问 |
| 事件信息 | 描述事件信息并提供对其元数据的访问 |
| PropertyInfo | 发现属性的属性并提供对属性元数据的访问 |
| 会员信息 | 获取有关成员属性的信息，并提供对成员元数据的访问 |

**注意:**还有很多其他类，上表只给出了常用的信息。

现在让我们看一个例子来描述反射在 C# 中是如何工作的。

**示例 1:** 在下面给出的代码中，我们使用 typeof 方法将 t 类型加载为字符串。然后我们在 t 上应用反射来找到任何关于字符串类的信息，比如它的名称、全名、名称空间和 basetype。

```cs
// C# program to illustrate
// the use of Reflection
using System;
using System.Reflection;

namespace Reflection_Demo {

class Program {

    // Main Method
    static void Main(string[] args)
    {
        // Initialise t as typeof string
        Type t = typeof(string);

        // Use Reflection to find about
        // any sort of data related to t
        Console.WriteLine("Name : {0}", t.Name);
        Console.WriteLine("Full Name : {0}", t.FullName);
        Console.WriteLine("Namespace : {0}", t.Namespace);
        Console.WriteLine("Base Type : {0}", t.BaseType);
    }
}
}
```

**输出:**

```cs
Name : String
Full Name : System.String
Namespace : System
Base Type : System.Object

```

**示例 2:** 在这段代码中，我们使用反射来显示与程序相关的所有元数据，这些元数据包括类、这些类的方法以及与这些参数相关联的参数。

```cs
// C# program to illustrate
// the use of Reflection
using System;
using System.Reflection;

namespace Reflection_Metadata {

// Define a class Student
class Student {

    // Properties definition
    public int RollNo
    {
        get;
        set;
    }

    public string Name
    {
        get;
        set;
    }

    // No Argument Constructor
    public Student()
    {
        RollNo = 0;
        Name = string.Empty;
    }

    // Parameterised Constructor
    public Student(int rno, string n)
    {
        RollNo = rno;
        Name = n;
    }

    // Method to Display Student Data
    public void displayData()
    {
        Console.WriteLine("Roll Number : {0}", RollNo);
        Console.WriteLine("Name : {0}", Name);
    }
}

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Declare Instance of class Assembly
        // Call the GetExecutingAssembly method
        // to load the current assembly
        Assembly executing = Assembly.GetExecutingAssembly();

        // Array to store types of the assembly
        Type[] types = executing.GetTypes();
        foreach(var item in types)
        {
            // Display each type
            Console.WriteLine("Class : {0}", item.Name);

            // Array to store methods
            MethodInfo[] methods = item.GetMethods();
            foreach(var method in methods)
            {
                // Display each method
                Console.WriteLine("--> Method : {0}", method.Name);

                // Array to store parameters
                ParameterInfo[] parameters = method.GetParameters();
                foreach(var arg in parameters)
                {
                    // Display each parameter
                    Console.WriteLine("----> Parameter : {0} Type : {1}",
                                            arg.Name, arg.ParameterType);
                }
            }
        }
    }
}
}
```

**输出:**

```cs
 Class : Student
--> Method : get_RollNo
--> Method : set_RollNo
----> Parameter : value  Type : System.Int32
--> Method : get_Name
--> Method : set_Name
----> Parameter : value  Type : System.String
--> Method : displayData
--> Method : ToString
--> Method : Equals
----> Parameter : obj  Type : System.Object
--> Method : GetHashCode
--> Method : GetType

 Class : Program
--> Method : ToString
--> Method : Equals
----> Parameter : obj  Type : System.Object
--> Method : GetHashCode
--> Method : GetType

```