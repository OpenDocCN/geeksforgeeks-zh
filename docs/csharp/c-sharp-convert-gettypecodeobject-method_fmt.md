# C# | Convert.GetTypeCode(Object)方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-convert-gettypecodeobject-method/](https://www.geeksforgeeks.org/c-sharp-convert-gettypecodeobject-method/)

该方法用于返回指定对象的`类型代码`。

## 语法：

```cs
public static TypeCode GetTypeCode (object value);
```

这里`value`是实现`IConvertible`接口的对象。

## 返回值：

该方法返回`value`的`TypeCode`，如果`value`为`null`，则返回`null`。

以下程序说明了`Convert.GetTypeCode(Object)`方法的使用：

## 示例 1：

```cs
// C# program to demonstrate
// Convert.GetTypeCode() Method
using System;

class GFG {

// Main Method
    public static void Main()
    {

// Declaring val1 and val2
        string val1;
        bool val2;

// initializing the
        // val1 and val2
        val1 = "abab";
        val2 = true;

// getting TypeCode
        // using Convert.GetTypeCode() method
        TypeCode t1 = Convert.GetTypeCode(val1);
        TypeCode t2 = Convert.GetTypeCode(val2);

// Display TypeCode
        Console.WriteLine("TypeCode of val1 is {0}", t1);
        Console.WriteLine("TypeCode of val2 is {0}", t2);
    }
}
```

**输出：**

```cs
TypeCode of val1 is String
TypeCode of val2 is Boolean
```

## 示例 2：

```cs
// C# program to demonstrate
// Convert.GetTypeCode() Method
using System;

class GFG {

// Main Method
    public static void Main()
    {

// Declaring val1 and val2
        char val1;
        float val2;

// initializing the
        // val1 and val2
        val1 = 'a';
        val2 = 20f;

// calling get() method
        get(val1);
        get(val2);
    }

// Defining the get() method
    public static void get(char val)
    {

// getting TypeCode
        // using Convert.GetTypeCode() method
        TypeCode t = Convert.GetTypeCode(val);

// Display the TypeCode
        Console.WriteLine("TypeCode of {0}"+
                         " is {1}", val, t);
    }
    public static void get(float val)
    {

// getting TypeCode
        // using GetTypeCode() method
        TypeCode t = Convert.GetTypeCode(val);

// Display the TypeCode
        Console.WriteLine("TypeCode of {0}"+
                         " is {1}", val, t);
    }
}
```

**输出：**

```cs
TypeCode of a is Char
TypeCode of 20 is Single
```

## 参考：

*   [https://docs.microsoft.com/en-us/dotnet/api/system.convert.gettypecode?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.convert.gettypecode?view=netframework-4.7.2)