# 在 C# 中使用反射的后期绑定

> 原文:[https://www . geesforgeks . org/late-binding-use-reflection-in-c-sharp/](https://www.geeksforgeeks.org/late-binding-using-reflection-in-c-sharp/)

上述主题中出现的两个主要术语是后期绑定和反射。让我们首先定义这两个术语。运行时方法和对象的绑定称为 [**【后期绑定】或**](https://www.geeksforgeeks.org/early-and-late-binding-in-c-sharp/) 。反射是程序集检查其元数据的能力。元数据包含程序集中数据的信息。
反射用于实现后期绑定，因为它允许您使用编译时不可用的代码。我们将在下面的代码段中看到这方面的例子。

**示例 1 :** 在这个程序中，我们使用了后期绑定，因为我们不知道在编译时必须实例化的类。声明一个名为执行类程序集的对象，并使用*方法加载当前程序集。接下来，我们必须找到稍后必须实例化的类的类型，即*学生*。为此，在 Assembly 类的对象上使用方法*获取类型*，并将该类型存储在另一个名为 *studentType* 的对象中。 *GetType* 方法需要一个字符串参数，它是类的完整名称， *LateBinding。学生*在这种情况下。由于该类型在程序中此时是未知的，我们使用类类型来声明 *studentType* 。现在我们使用 *CreateInstance* 方法创建 studentType 的实例，该方法使用类型作为参数。Activator 类包含在本地或远程创建对象类型或获取对现有远程对象的引用的方法。接下来，创建一个 *MethodInfo* 对象，并使用 GetMethod 方法存储信息。将方法的名称作为参数传递给 *GetMethod* 。要调用 GetDetails，使用 MethodInfo 对象调用 invoke 方法，并将 *studentObject* 作为参数传递。最后，使用字符串 *det* 显示细节并定义类。*

## C#

```cs
// C# program to show the Late
// Binding using Reflection
using System;
using System.Reflection;

namespace LateBinding {

class Program {

    // Main Method
    static void Main(string[] args)
    {
        // Declare Instance of class Assembly
        // Call the GetExecutingAssembly method
        // to load the current assembly
        Assembly executing = Assembly.GetExecutingAssembly();

        // To find the type of the Class Student
        Type studentType = executing.GetType("LateBinding.Student");

        // Create an Instance of the Student type
        object studentObject = Activator.CreateInstance(studentType);

        // Store the info of the method in an object
        // of class MethodInfo
        MethodInfo getMethod = studentType.GetMethod("GetDetails");

        // To store the parameters required
        // by Method GetDetails
        String[] param = new String[2];
        param[0] = "1";
        param[1] = "Lisa";

        // To display the result of the method
        String det = (String)getMethod.Invoke(studentObject, param);
        Console.WriteLine("Student Details : ");
        Console.WriteLine("Roll Number - Name \n{0}", det);

    } // end Main

} // end Program

public class Student {

    public String GetDetails(String RollNumber, String Name)
    {
        return RollNumber + " - " + Name;
    }

} // end Student

}
```

**Output:** 

```cs
Student Details : 
Roll Number - Name 
1 - Lisa
```

**注意:**在上面的代码中，如果您没有定义类并构建代码，它将成功构建，因为绑定不是在编译时完成的。但是当你运行它时，你会得到一个错误，因为它只会在运行时遇到。错误消息如下；

> 未处理的异常:系统。ArgumentNullException:值不能为空。
> 参数名称:在系统处输入
> 。激活器。在系统上创建实例(类型类型，布尔非公共)
> 。激活器。在后期绑定时创建实例(类型)
> 。m:\ Documents \ Visual Studio 2012 \ project \ late binding \ late binding \ program . cs:第 19 行

**示例 2:** 另一个类似的示例是下面给出的代码，它有一个 Shape 类，我们后期绑定了 shapeName 方法。

## C#

```cs
// C# program to show the Late
// Binding using Reflection
using System;
using System.Reflection;

namespace Geometry {

// class Shape
public class Shape {

    // Function that gives the name of the
    // shape based on the number of sides
    // the number of sides is a string that
    // contains the value
    public String shapeName(String sideNumber)
    {
        if (sideNumber == "0" || sideNumber == "1" || sideNumber == "2")
            return "Not Valid";
        else if (sideNumber == "3")
            return "Triangle";
        else if (sideNumber == "4")
            return "Quadrilateral";
        else
            return "Polygon";
    }

} // end Shape

class Program {

    // Main Method
    static void Main(string[] args)
    {
        // Object of Assembly class
        Assembly executable = Assembly.GetExecutingAssembly();

        // To find the type of the class
        Type shapeType = executable.GetType("Geometry.Shape");

        // To create an instance of Shape class
        // without prior information about it
        object shapeObject = Activator.CreateInstance(shapeType);

        // To find the info about the method
        MethodInfo shapeNameMethod = shapeType.GetMethod("shapeName");

        // Prepare parameters for the method
        String[] param = new String[1];
        param[0] = "4";

        // To invoke the method using Invoke
        String sName = (String)shapeNameMethod.Invoke(shapeObject, param);

        // To  display the name of the shape
        Console.WriteLine("Name of the Shape is {0}", sName);

    } // end Main

} // end Program

}
```

**Output:** 

```cs
Name of the Shape is Quadrilateral
```

**注意:**后期绑定的*缺点是如果你在一个方法或类的名字中有任何拼写错误，编译器在编译时不会识别它，因此代码会成功构建。在大多数实际场景中，使用早期绑定，而不是后期绑定。*