# C# Type.GetDefaultMembers() 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-type-getdefaultmembers-method/](https://www.geeksforgeeks.org/c-sharp-type-getdefaultmembers-method/)

## 方法说明

`Type.GetDefaultMembers()` 方法用于查找为当前类型定义的成员，该类型的 `DefaultMemberAttribute` 被设置。

### 语法

```cs
public virtual MemberInfo[] GetDefaultMembers();
```

### 返回值

如果当前类型没有默认成员，该方法返回一个表示当前类型所有默认成员的 `MemberInfo` 对象数组或一个 `MemberInfo` 类型的空数组。

## 示例

以下程序说明了 `Type.GetDefaultMembers()` 方法的使用：

### 例 1

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
            Console.WriteLine("Result is:  {0}", info[i]);
    }
}
```

**输出：**

```cs
Result is:  Char Chars [Int32]
```

### 例 2

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
                Console.WriteLine("Result is:  {0}", info[i]);
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

**输出：**

```cs
Result is:  System.String name
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.type.getdefaultmembers?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.type.getdefaultmembers?view=netframework-4.8)