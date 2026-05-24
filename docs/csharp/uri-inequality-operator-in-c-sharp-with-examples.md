# 乌利。C# 中的不等式()运算符及示例

> 原文:[https://www . geesforgeks . org/uri-不等式-运算符-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uri-inequality-operator-in-c-sharp-with-examples/)

**乌利。不等式()运算符**用于比较两个 Uri 对象。如果两个 Uri 对象包含相同的 Uri，则返回 ***假*** ，否则返回 ***真*** 。

***语法:***

```cs
public static bool operator != (Uri uri1, Uri uri2);

```

**参数:**该方法有以下参数:

> **uri1:** 此参数是第一个要比较的 uri。
> 
> **uri2:** 此参数是要比较的第二个 uri。

**返回值:**该方法返回布尔值。如果 Uri 实例不相等，则返回 true，否则返回 false。

下面的程序说明了 Uri 的使用。不等式()运算符:

**例 1:**

## C#

```cs
// C# program to demonstrate the 
// Uri.Inequality() Operator

using System;  

class GFG { 

    // Main Method 
    public static void Main() 
    { 
        // Declaring and initializing address1 
        Uri address1 = new Uri("http://www.gfg.com/index.htm# search"); 

        // Declaring and intializing address2 
        Uri address2 = new Uri("http://www.gfg.com/index.htm"); 

        // Comparing both instance 
        // using Uri.Inequality() Operator
        if (address1 != address2)
            Console.WriteLine("address1 is not Equals to address2"); 
        else
            Console.WriteLine("address1 is Equals to address2"); 
    } 
} 
```

**输出:**

```cs
address1 is Equals to address2

```

**例 2:**

## C#

```cs
// C# program to demonstrate the 
// Uri.Inequality() Operator

using System;  

class GFG { 

    // defining get_Inequality() method 
    public static void get_Inequality(Uri address1, 
                           Uri address2) 
    { 

        // Comparing both instance 
        // using Uri.Inequality() Operator
        if (address1 != address2) 
            Console.WriteLine("{0} is not Equals to {1}", address1, address2); 
        else
            Console.WriteLine("{0} is Equals to {1}", address1, address2); 
    } 

    // Main Method 
    public static void Main() 
    { 
        // calling get_Inequality() method 
        get_Inequality(new Uri("http://www.gfg.com"), 
            new Uri("http://www.gfg.com")); 

        get_Inequality(new Uri("http://www.abcd.com"),  
            new Uri("https://www.geeksforgeeks.org"));  
    } 
} 
```

**输出:**

```cs
http://www.gfg.com/ is Equals to http://www.gfg.com/
http://www.abcd.com/ is not Equals to https://www.geeksforgeeks.org/

```