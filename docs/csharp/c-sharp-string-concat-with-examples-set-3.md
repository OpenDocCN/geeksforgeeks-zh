# C# |字符串 Concat 带示例| Set-3

> 原文:[https://www . geesforgeks . org/c-sharp-string-concat-with-examples-set-3/](https://www.geeksforgeeks.org/c-sharp-string-concat-with-examples-set-3/)

**弦。连接方法**用于连接一个或多个[字符串](https://www.geeksforgeeks.org/c-string/)的实例或一个或多个对象实例的值的[字符串](https://www.geeksforgeeks.org/c-string/)表示。它总是返回串联字符串。
这个方法可以通过传递不同类型和数量的参数来重载。Concat 方法的重载列表中共有 **11** 种方法，其中前 6 种在**[Set-1](https://www.geeksforgeeks.org/c-string-concat-with-examples-set-1/)&[Set-2](https://www.geeksforgeeks.org/c-string-concat-with-examples-set-2/)**中讨论，其余在 **Set-3 和 Set-4** 中讨论。

##### 7.连接(对象[])

此方法用于连接指定对象数组中元素的字符串表示形式。

**注意:**如果数组包含空对象，则**字符串。空**用于代替空对象。

**语法:**

```cs
public static string Concat (params object[] arg);
```

这里， *arg* 是一个包含要连接的元素的对象数组。

**返回值:**该方法的返回类型为**系统。弦**。此方法返回代表*参数*中元素值的串联字符串。

例外:

*   如果给定的*参数*的值为空，则该方法将给出*参数空异常*。
*   如果数组内存不足，那么这个方法会给出 *OutOfMemoryException* 。

**示例:**

```cs
// C# program to illustrate 
// the Concat(object[]) Method
using System;

// class declaration
class EmptyA { }

class GFG {

    // Main method
    public static void Main()
    {
        // creating object of EmptyA class
        EmptyA g1 = new EmptyA();

        string strA = " GeeksforGeeks ";

        object[] ob = {21, " Hello!", strA, g1};

        // print elements of object array
        // using Concat(object[]) Method
        Console.WriteLine("Elements of object array : {0}",
                                        string.Concat(ob));
    }
}
```

**输出:**

```cs
Elements of object array : 21 Hello! GeeksforGeeks EmptyA
```

##### 8.连接(对象)

此方法用于创建指定对象的字符串表示形式。

**语法:**

```cs
public static string Concat (object argA);
```

这里， *argA* 是要表示的对象，或者 null。

**返回值:**该方法的返回类型为**系统。弦**。该方法返回表示存在于 *argA* 中的元素的值的串联字符串，或者如果 *argA* 为空，则返回*空*。

**示例:**

```cs
// C# program to illustrate the
// Concat(object) Method
using System;

class GFG {

    // Main method
    public static void Main()
    {

        // string
        string strA = "Geeks";

        // assigning string to object
        object ob = strA;

        // object array
        Object[] objs = new Object[] {"1", "2"};

        // using Concat(object) method
       Console.WriteLine("Concatenate 1, 2, and 3 objects:");
       Console.WriteLine("1: {0}", String.Concat(ob));
       Console.WriteLine("2: {0}", String.Concat(ob, ob));
       Console.WriteLine("3: {0}", String.Concat(ob, ob, ob));

       Console.WriteLine("Concatenate two element object array: {0}", String.Concat(objs));
    }
}
```

**输出:**

```cs
Concatenate 1, 2, and 3 objects:
1: Geeks
2: GeeksGeeks
3: GeeksGeeksGeeks
Concatenate two element object array: 12

```

##### 9.连接(对象，对象)

此方法用于连接两个指定对象的字符串表示形式。

**语法:**

```cs
public static string Concat (object argA, object argB);
```

**参数:**

> **argA** :第一个要连接的对象。
> **argB** :第二个要连接的对象。

**返回值:**该方法的返回类型为**系统。弦**。串联字符串表示参数列表中的每个值。

**示例:**

```cs
// C# program to illustrate
// Concat(object, object) Method
using System;

class GFG {

    // Main method
    public static void Main()
    {

        // string
        string strA = "50";

        // object
        object ob = strA;

        // object array
        Object[] objs = new Object[] {"34", "87"};

        // Concatenating two objects
        // using Concat(object, object) method
        Console.WriteLine("Concatenate two objects: {0}",
                                  String.Concat(ob, ob));

        Console.WriteLine("Concatenate two element object array: {0}",
                                                 String.Concat(objs));
    }
}
```

**输出:**

```cs
Concatenate two objects: 5050
Concatenate two element object array: 3487

```

**参考:**T2？视图=netframework-4.7.2