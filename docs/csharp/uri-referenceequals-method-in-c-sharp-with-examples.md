# 乌利。参考 C# 中的 quals()方法并举例

> 原文:[https://www . geesforgeks . org/uri-referenceeqals-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/uri-referenceequals-method-in-c-sharp-with-examples/)

**乌利。参考质量()方法**用于检查两个指定对象的参考。该方法可以被覆盖，本质上是静态的。因此，如果用户要测试两个对象引用是否相等，并且他不确定 *Equals* 方法的实现，那么他可以调用 *ReferenceEquals* 方法。

> *语法* 布尔型 uri . reference quals(uri 1、uri 2)；
> 
> ***参数:***
> **uri1** *:是第一个比较的 uri。*
> **uri2** *:是第二个比较的 uri。*
> 
> ***返回值:**如果两个对象的引用相等，则该方法返回真* ，否则返回假。

下面的程序说明了 **Uri 的使用。参考质量()**方法:

**例 1:**

## C#

```cs
// C# program to demonstrate the 
// Uri.ReferenceEquals() Method 
using System; 
using System.Globalization; 

class GFG { 

     // Main Method 
    public static void Main() 
    { 
        // Declaring and initializing value1 
        Uri  v1 = null; 

        // Declaring and initializing value2 
        Uri  v2 = null; 

        // using ReferenceEquals(Uri , 
        // Uri ) method 
        bool status = Uri.ReferenceEquals(v1, v2); 

        // checking the status 
        if (status) 
            Console.WriteLine("null is equal to null"); 
        else
            Console.WriteLine("null is not equal to null"); 
    } 
}
```

**输出:**

```cs
null is equal to null

```

**例 2:**

## C#

```cs
// C# program to demonstrate the 
// Uri.ReferenceEquals() Method 
using System; 
using System.Globalization; 

class GFG { 

    // Main Method 
    public static void Main() 
    { 

        Uri  p = new Uri("https://www.geeksforgeeks.org/index.htm"); 
        Uri  q = null; 

        // calling get() method 
        get(p, null); 

        // assigning p to q 
        q = p; 
        get(p, q); 
        get(q, null); 
    } 

    // defining get() method 
    public static void get(Uri  v1, 
                           Uri  v2) 
    { 

        // using ReferenceEquals() method 
        bool status = Uri.ReferenceEquals(v1, v2); 

        // checking the status 
        if (status) 
            Console.WriteLine("{0} is equal to {1}", 
                                            v1, v2); 
        else
            Console.WriteLine("{0} is not equal to {1}", 
                                                v1, v2); 
    } 
}
```

**输出:**

```cs
https://www.geeksforgeeks.org/index.htm is not equal to 
https://www.geeksforgeeks.org/index.htm is equal to https://www.geeksforgeeks.org/index.htm
https://www.geeksforgeeks.org/index.htm is not equal to 

```

**注意:**这里， *null* 永远不会打印在输出中。