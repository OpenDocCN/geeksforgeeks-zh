# 乌利。C# 中的等式()运算符及示例

> 原文:[https://www . geesforgeks . org/uri-equality-operator-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uri-equality-operator-in-c-sharp-with-examples/)

**乌利。等式()运算符** 用于比较两个 Uri 对象。如果两个 Uri 对象包含相同的 Uri，则返回 ***真*** ，否则返回 ***假*** 。

***语法:***

```cs
public static bool operator == (Uri uri1, Uri uri2);

```

**参数:**该方法有以下参数:

> **uri1:** 此参数是 第一个要比较的 Uri。
> 
> **uri2:** 这个参数是 第二个要比较的 uri。

**返回值:**该方法返回布尔值。如果 Uri 实例相等，则返回真，否则返回假。

以下程序说明了 Uri 的使用。等式()运算符:

**例 1:**

## C#

```cs
// C# program to demonstrate the 
// Uri.Equality() Operator

using System;  

class GFG { 

    // Main Method 
    public static void Main() 
    { 
        // Declaring and initializing address1 
        Uri address1 = new Uri("http://www.abcs.com/index.htm# search"); 

        // Declaring and intializing address2 
        Uri address2 = new Uri("http://www.abcd.com/index.htm"); 

        // Comparing both instance 
        // using Uri.Equality() Operator
        if (address1 == address2)
            Console.WriteLine("address1 is Equals to address2"); 
        else
            Console.WriteLine("address1 is not Equals to address2"); 
    } 
}
```

**Output**

```cs
address1 is not Equals to address2

```

**例 2:**

## C#

```cs
// C# program to demonstrate the 
// Uri.Equality() Operator

using System;  

class GFG { 

    // defining get_equality() method 
    public static void get_equality(Uri address1, 
                           Uri address2) 
    { 

        // Comparing both instance 
        // using Uri.Equality() Operator
        if (address1 == address2) 
            Console.WriteLine("{0} is Equals to {1}", address1, address2); 
        else
            Console.WriteLine("{0} is not Equals to {1}", address1, address2); 
    } 

    // Main Method 
    public static void Main() 
    { 
        // calling get_equality() method 
        get_equality(new Uri("http://www.abcd.com"), 
            new Uri("http://www.abcd.com")); 

        get_equality(new Uri("http://www.google.com"),  
            new Uri("http://www.facebook.com"));  
    } 
}
```

**Output**

```cs
http://www.abcd.com/ is Equals to http://www.abcd.com/
http://www.google.com/ is not Equals to http://www.facebook.com/

```