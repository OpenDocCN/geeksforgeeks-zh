# C# |类型。GetNestedTypes()方法

> 原文:[https://www . geesforgeks . org/c-sharp-type-getnestedtypes-method/](https://www.geeksforgeeks.org/c-sharp-type-getnestedtypes-method/)

**类型。方法**用于获取嵌套在当前类型中的类型。此方法的重载列表中有 2 种方法，如下所示:

#### GetNestedTypes()方法

此方法用于返回嵌套在当前类型中的公共类型。

> **语法:**公共类型[]GetNestedTypes()；
> **返回值:**该方法返回一个 type 对象数组，表示嵌套在当前 Type 中的公共类型(搜索不是递归的)，如果当前 Type 中没有嵌套公共类型，则返回 Type 的空数组。

下面的程序说明了上述方法的使用:
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Type.GetNestedTypes() Method
using System;
using System.Globalization;
using System.Reflection;

// Defining class Empty
public class Empty { }

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing object of Type
        Type objType = typeof(Person);

        // try-catch block for handling Exception
        try {

            // Getting array of Method by
            // using GetMethods() Method
            Type[] type = objType.GetNestedTypes();

            // Display the Result
            Console.WriteLine("NestedType of current type is: ");
            for (int i = 0; i < type.Length; i++)
                Console.WriteLine("{0} ", type[i]);
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

public class Person {

    public class Student
    {
        // string name;
        // int roll;
        // string dept;
    }

    public class Teacher
    {
        // string name;
        // string dept;
        // int id;
    }
}
```

**Output:** 

```cs
NestedType of current type is: 
Person+Student 
Person+Teacher
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Type.GetNestedTypes() Method
using System;
using System.Globalization;
using System.Reflection;

// Defining class Empty
public class Empty { }

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing object of Type
        Type objType = typeof(Animal);

        // try-catch block for handling Exception
        try {

            // Getting array of Method by
            // using GetMethods() Method
            Type[] type = objType.GetNestedTypes();

            // Display the Result
            Console.WriteLine("NestedType of current type is: ");
            for (int i = 0; i < type.Length; i++)
                Console.WriteLine(" {0}", type[i]);
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

public class Animal {

    public class Cat {

        // string breed;
        // string color;
        // string type;
    }

    public class Dog {

        // string breed;
        // string color;
        // string type;
    }

    public class Mouse {

        // string breed;
        // string color;
        // string type;
    }

    public interface Description {

        string getBreed();
        string getColor();
        string getType();
        bool isAlive();
    }
}
```

**Output**

```cs
NestedType of current type is: 
 Animal+Cat
 Animal+Dog
 Animal+Mouse
 Animal+Description

```

#### 方法

当在派生类中重写时，使用指定的绑定约束，此方法用于搜索嵌套在当前类型中的类型。

> **语法:**公共抽象类型[] GetNestedTypes(系统。反射. binding flags binding attr)；
> 这里，需要一个由一个或多个 BindingFlags 组成的位掩码来指定如何进行搜索，或者使用 Zero 来返回 null。
> **返回值:**该方法返回一个类型对象数组，表示嵌套在当前类型中符合指定绑定约束的所有类型(搜索不是递归的)，如果没有找到符合绑定约束的嵌套类型，则返回类型类型的空数组。

**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Type.GetNestedTypes() Method
using System;
using System.Globalization;
using System.Reflection;

// Defining class Empty
public class Empty { }

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing object of Type
        Type objType = typeof(Animal);

        // try-catch block for handling Exception
        try {

            // Getting array of Method by
            // using GetMethods() Method
            Type[] type = objType.GetNestedTypes();

            // Display the Result
            Console.WriteLine("NestedType of current type is: ");
            for (int i = 0; i < type.Length; i++)
                Console.WriteLine(" {0}", type[i]);
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

public class Animal {

    public class Cat {

        // string breed;
        // string color;
        // string type;
    }

    public class Dog {

        // string breed;
        // string color;
        // string type;
    }

    public class Mouse {

        // string breed;
        // string color;
        // string type;
    }

    public interface Description {

        string getBreed();
        string getColor();
        string getType();
        bool isAlive();
    }
}
```

**Output:** 

```cs
NestedType of current type is: 
 Animal+Empty
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Type.GetNestedTypes() Method
using System;
using System.Globalization;
using System.Reflection;

// Defining class Empty
public class Empty { }

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing object of Type
        Type objType = typeof(Person);

        // try-catch block for handling Exception
        try {

            // Getting array of Method by
            // using GetMethods() Method
            Type[] type = objType.GetNestedTypes(BindingFlags.Public);

            // Display the Result
            Console.WriteLine("NestedType of current type is: ");

            for (int i = 0; i < type.Length; i++)
                Console.WriteLine(" {0}", type[i]);
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

public class Person {

    public class Student
    {
        // string name;
        // int roll;
        // string dept;
    }

    public class Teacher
    {
        // string name;
        // string dept;
        // int id;
    }
}
```

**Output:** 

```cs
NestedType of current type is: 
 Person+Student
 Person+Teacher
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . getnested types？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.getnestedtypes?view=netframework-4.8)