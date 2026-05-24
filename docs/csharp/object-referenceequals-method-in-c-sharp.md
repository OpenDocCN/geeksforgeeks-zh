# 物体。参考 C# 中的 quals()方法

> 原文:[https://www . geeksforgeeks . org/object-referencequals-method-in-c-sharp/](https://www.geeksforgeeks.org/object-referenceequals-method-in-c-sharp/)

**物体。参考质量()方法**用于确定指定的对象实例是否为同一实例。不能重写此方法。因此，如果用户要测试两个对象引用是否相等，并且他不确定 *Equals* 方法的实现，那么他可以调用 *ReferenceEquals* 方法。

> **语法:**公共静态 bool referencequals(object ob1，object ob2)；
> 
> **参数:**
> **ob1** :是第一个比较的对象。
> **ob2** :是第二个比较的对象。
> 
> **返回值:**如果 *ob1* 与 *ob2* 是同一个实例，或者两者都为*空*，则该方法返回*真*，否则返回*假*。

以下程序说明了**对象的使用。参考质量()**方法:

**例 1:**

```cs
// C# program to demonstrate the
// Object.ReferenceEquals(object)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {
        // Declaring and initializing value1
        object v1 = null;

        // Declaring and initializing value2
        object v2 = null;

        // using ReferenceEquals(object,
        // object) method
        bool status = Object.ReferenceEquals(v1, v2);

        // checking the status
        if (status)
            Console.WriteLine("null is equal to null");
        else
            Console.WriteLine("null is not equal to null");
    }
}
```

**Output:**

```cs
null is equal to null

```

**例 2:**

```cs
// C# program to demonstrate the
// Object.ReferenceEquals(Object, Object)
// Method
using System;
using System.Globalization;

class GFG {

    // Main Method
    public static void Main()
    {

        object p = new Object();
        object q = null;

        // calling get() method
        get(p, null);

        // assigning p to q
        q = p;
        get(p, q);
        get(q, null);
    }

    // defining get() method
    public static void get(object v1,
                           object v2)
    {

        // using ReferenceEquals(Object) method
        bool status = Object.ReferenceEquals(v1, v2);

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

**Output:**

```cs
System.Object is not equal to 
System.Object is equal to System.Object
System.Object is not equal to 

```

**注意:**这里， *null* 永远不会打印在输出中。

**要点:**

*   如果 *ob1* 和 *ob2* 都表示值类型的相同实例，则该方法仍然返回 false。
*   如果 *ob1* 和 *ob2* 是字符串，那么如果字符串是内部字符串，该方法将返回 *true* ，因为该方法永远不会执行值相等的测试。

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . object . reference quals？view=netcore-2.1](https://docs.microsoft.com/en-us/dotnet/api/system.object.referenceequals?view=netcore-2.1)