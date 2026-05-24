# C# |类型。GetDefaultMembers()方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-type-getdefaultmembers-method/](https://www.geeksforgeeks.org/c-sharp-type-getdefaultmembers-method/)

**类型。GetDefaultMembers()方法**用于查找为当前类型定义的成员，该类型的 DefaultMemberAttribute 被设置。

> **语法:**公共虚拟系统。反射. MemberInfo[]GetDefaultMembers()；
> 
> **返回值:**如果当前类型没有默认成员，该方法返回一个表示当前类型所有默认成员的**成员信息**对象数组或一个成员信息类型的空数组。

以下程序说明了*类型的使用。GetDefaultMembers()* 方法:

**例 1:**

```cs
// C# program to demonstrate the
// Type.GetDefaultMembers() Method
using System;
using System.Globalization;
using System.Reflection;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing obj
        object obj = "Ram";

        // Getting the type of obj
        // using GetType() Method
        Type type = obj.GetType();

        // Getting the DefaultMembers
        // using GetDefaultMembers() Method
        MemberInfo[] info = type.GetDefaultMembers();

        // Display the result
        for (int i = 0; i < info.Length; i++)

            Console.WriteLine("Result is:  {0}", info[i]);
    }
}
```

**Output:**

```cs
Result is:  Char Chars [Int32]

```

**例 2:**

```cs
// C# program to demonstrate the
// Type.GetDefaultMembers() Method
using System;
using System.Globalization;
using System.Reflection;

// Setting DefaultMemberAttribute
[DefaultMemberAttribute("name")] class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing
        // object of Type dataType
        Type type = typeof(GFG);

        // Getting the DefaultMembers
        // using GetDefaultMembers() Method
        MemberInfo[] info = type.GetDefaultMembers();

        if (info.Length != 0)
        {
            for (int i = 0; i < info.Length; i++)
                Console.WriteLine("Result is:  {0}", info[i]);
        }
        else {
            Console.WriteLine("DefaultMember is not found");
        }
    }

    // Defining Member Attributes
    public void Name(String s) {}

    // Defining property
    public String name
    {
        // property or indexer must 
        // have at least one accessor
        get
        {
            return "Ram";
        }
    }
}
```

**Output:**

```cs
Result is:  System.String name

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . type . getdefaultmembers？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.getdefaultmembers?view=netframework-4.8)