# 类型。C# 中的 GetConstructors()方法及示例

> 原文:[https://www . geesforgeks . org/type-getconstructors-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/type-getconstructors-method-in-c-sharp-with-examples/)

**类型。GetConstructors()方法**用于获取 Type 对象的构造函数。该方法重载列表中有 2 种方法如下:

#### 打字。GetConstructors()方法

此方法用于返回为当前类型定义的所有公共构造函数。
**语法:**

```cs
public System.Reflection.ConstructorInfo[] GetConstructors ();
```

**返回:**该方法返回 *ConstructorInfo* 数组对象，表示为当前类型定义的所有公共实例构造函数，但不包括类型初始值设定项(静态构造函数)。
以下程序说明了**型的使用。GetConstructors()** 方法:
**示例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Type.GetConstructors() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing object
        object obj = new Object();

        // Getting the type of object
        // using GetType() method
        Type type = obj.GetType();

        // Getting constructors of the current Type.
        // using GetArrayRank() Method
        ConstructorInfo[] info = type.GetConstructors();

        // Display all the public instance constructors
        Console.WriteLine("All constructors are shown below");

        for (int i = 0; i < info.Length; i++)
            Console.WriteLine(info[i]);
    }
}
```

**Output:** 

```cs
All constructors are shown below
Void .ctor()
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Type.GetConstructors() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing Type object
        Type type = typeof(string);

        // Getting constructors of the current Type.
        // using GetConstructors() Method
        ConstructorInfo[] info = type.GetConstructors();

        // Display all the public instance constructors
        Console.WriteLine("All constructors are shown below");

        for (int i = 0; i < info.Length; i++)
            Console.WriteLine(info[i]);
    }
}
```

**Output:** 

```cs
All constructors are shown below
Void .ctor(Char[])
Void .ctor(Char[], Int32, Int32)
Void .ctor(Char*)
Void .ctor(Char*, Int32, Int32)
Void .ctor(SByte*)
Void .ctor(SByte*, Int32, Int32)
Void .ctor(SByte*, Int32, Int32, Encoding)
Void .ctor(Char, Int32)
Void .ctor(ReadOnlySpan`1)
```

#### 打字。方法

此方法用于返回为当前类型定义的构造函数，当在派生类中被重写时，使用指定的 BindingFlags，
**语法:**

> 公共抽象系统。反射. ConstructorInfo[]GetConstructors(系统。反射. binding flags binding attr)；

这里，它采用了一个由一个或多个绑定标志组成的位掩码，这些标志指定了参加的时间点。或零，返回空值。
以下是一些*绑定标签*过滤器标志，可用于定义搜索中包括哪些构造函数:

*   您必须指定*绑定标签。实例*或*装订标签。静态*为了得到回报。
*   指定*绑定标签。公共*在搜索中包含公共构造函数。
*   指定*绑定标签。非公共*在搜索中包含非公共构造函数(即私有、内部和受保护的构造函数)。不返回基类的构造函数。

**返回值:**这个方法返回一个 *ConstructorInfo* 对象的数组，表示为当前类型定义的所有符合指定绑定约束的构造函数，包括类型初始值设定项(如果定义的话)。
以下程序说明了上述方法的使用:
**例 1:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Type.GetConstructors(BindingFlags)
// Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing Type object
        Type type = typeof(string);

        // Declaring and initializing BindingFlags
        // it is used to specify how the search
        // is conducted
        BindingFlags bf = BindingFlags.Public
                          | BindingFlags.Static
                          | BindingFlags.NonPublic
                          | BindingFlags.Instance;

        // Getting constructors of the current Type.
        // using GetConstructors() Method
        ConstructorInfo[] info = type.GetConstructors(bf);

        // Display all constructors
        Console.WriteLine("All constructors are shown below");

        for (int i = 0; i < info.Length; i++)
            Console.WriteLine(info[i]);
    }
}
```

**Output:** 

```cs
All constructors are shown below
Void .ctor(Char[])
Void .ctor(Char[], Int32, Int32)
Void .ctor(Char*)
Void .ctor(Char*, Int32, Int32)
Void .ctor(SByte*)
Void .ctor(SByte*, Int32, Int32)
Void .ctor(SByte*, Int32, Int32, Encoding)
Void .ctor(Char, Int32)
Void .ctor(ReadOnlySpan`1)
```

**例 2:**

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// Type.GetConstructors(BindingFlags)
// Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {
        // Creating and initializing object
        object obj = new Object();

        // Declaring and initializing Type object
        Type type = obj.GetType();

        // Declaring and initializing BindingFlags
        // it is used to specify how the search is conducted
        BindingFlags bf = BindingFlags.Public
                          | BindingFlags.Static
                          | BindingFlags.NonPublic
                          | BindingFlags.Instance;

        // Getting constructors of the current Type.
        // using GetConstructors() Method
        ConstructorInfo[] info = type.GetConstructors(bf);

        // Display all constructors
        Console.WriteLine("All constructors are shown below");

        for (int i = 0; i < info.Length; i++)
            Console.WriteLine(info[i]);
    }
}
```

**Output:** 

```cs
All constructors are shown below
Void .ctor()
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . getconstructors？view=netcore-3.0](https://docs.microsoft.com/en-us/dotnet/api/system.type.getconstructors?view=netcore-3.0)